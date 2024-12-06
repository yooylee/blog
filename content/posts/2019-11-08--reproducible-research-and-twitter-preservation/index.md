---
title: "Twitter preservation and replicable research"
date: "2019-11-08"
template: "post"
draft: false
slug: "/posts/twitter-preservation-and-replicable-research"
category: "Digital Preservation"
tags:
  - "Digital preservation"
  - "Twitter preservation"
  - "Reproducible research"
  - "Replicable research"

description: "This blog post is about my journey to learning a new tool called twarc for Twitter preservation by replicating research conducted by Nick Ruest and Ian Milligan with new Twitter datasets (Open Access Week 2019)."

socialImage: "./wordcloud.png"

---

After several failed tries to preserve Twitter communication on a local incident using Archive-It (probably I did something wrong), I explored other tools such as <a href="https://github.com/DocNow/twarc">twarc</a> developed by Ed Summers. Due to the Twitter API limitations, I can't use it for the past incident, but I would like to learn for the future. For me, the best way to learn is to try.

I discovered an article - <a href="https://journal.code4lib.org/articles/11358">An Open-Source Strategy for Documenting Events: The Case Study of the 42nd Canadian Federal Election on Twitter</a> which introduces tools and approaches of how to use twarc and other tools to document events expressed via Twitter. Since it was the Open Access Week from October 21 to October 27, 2019, I replicated their study using Twitter with `#oaweek`, `#oaweek19`, `#oaweek2019`, `#openaccessweek`, and `#openaccessweek2019` hashtags collected on October 25 and 26, 2019.

### 1. Data collection

I used twarc search function to collect Twitter data.

```
twarc search '#oaweek' > oaweek.jsonl
twarc search '#oaweek19' > oaweek19.jsonl
twarc search '#oaweek2019' > oaweek2019.jsonl
twarc search '#openaccessweek' > openaccessweek.jsonl
twarc search '#openaccessweek2019' > openaccessweek2019.jsonl
```

```
twarc search '#oaweek' > oaweek_1026.jsonl
twarc search '#oaweek19' > oaweek19_1026.jsonl
twarc search '#oaweek2019' > oaweek2019_1026.jsonl
twarc search '#openaccessweek' > openaccessweek_1026.jsonl
twarc search '#openaccessweek2019' > openaccessweek2019_1026.jsonl
```

Then, I combined all these files to one file called `all_combined_oaweek_2019.jsonl` and created the final version called `deduped.jsonl` using `deduplicate.py` utility from twarc to remove any tweets with duplicate IDs.

```
cat oaweek.jsonl oaweek19.jsonl oaweek2019.jsonl openaccessweek.jsonl openaccessweek2019.jsonl oaweek_1026.jsonl oaweek19_1026.jsonl oaweek2019_1026.jsonl openaccessweek_1026.jsonl openaccessweek2019_1026.jsonl > all_combined_oaweek_2019.jsonl

utils/deduplicate.py all_combined_oaweek_2019.jsonl > deduped.jsonl
```

There were 24,041 tweets in the final dataset.

### 2. Processing

In order to unshorten every URL in the dataset, `unshorten.py` from twarc utilities in combination with <a href="https://github.com/DocNow/unshrtn">unshrtn</a> was applied.

```
docker run -p 3000:3000 docnow/unshrtn

cat deduped.jsonl | python3 twarc/utils/unshorten.py > deduped-unshortened.jsonl
```

### 3. Data analysis and results

#### Text

`wordcloud.py` utility from twarc was used to create a word cloud of tweets from the Open Access Week dataset.

**Wordcloud**
![Wordcloud images](/wordcloud.png)

#### Retweets

I was able to see the most retweets below:

```
utils/retweets.py deduped.jsonl > deduped-retweets.jsonl
utils/tweet_urls.py deduped.jsonl > deduped-retweets.txt
```

+ <a href="https://twitter.com/IEEEXplore/status/1186129985376907266">https://twitter.com/IEEEXplore/status/1186129985376907266</a> (327 retweets)
+ <a href="https://twitter.com/CUPAcademic/status/1186982898227929088">https://twitter.com/CUPAcademic/status/1186982898227929088</a> (240 retweets)
+ <a href="https://twitter.com/unpaywall/status/1186446881678708736">https://twitter.com/unpaywall/status/1186446881678708736</a> (181 retweets)
+ <a href="https://twitter.com/NobelPrize/status/1188096448556163073">https://twitter.com/NobelPrize/status/1188096448556163073</a> (161 retweets)
+ <a href="https://twitter.com/mchris4duke/status/1187021445597204480">https://twitter.com/mchris4duke/status/1187021445597204480</a> (104 retweets)

#### Geographic information

I ran the code as suggested by the article, but there were only 97 tweets who provided geographic information so I skipped it.

```
utils/geo.py deduped.jsonl > deduped-geo.jsonl
cat deduped-geo.jsonl | wc -l
#97
```

#### Users

Using `users.py` from twarc utility, I was able to identify Twitter users who tweets most around open access week.

```
utils/users.py deduped.jsonl > deduped-users.txt
cat deduped-users.txt | sort | uniq -c | sort -n > deduped-users-uniq.txt
cat deduped-users-uniq.txt | wc -l
#10078
tail dedupled-users-uniq.txt
```

+ Matthew Rimer [DrRimmer] (216 tweets)
+ AOASG [openaccess_anz] (161 tweets)
+ Open Book Publishers [OpenBookPublish] (105 tweets)
+ Dr Tseen Khoo [tseenster] (96 tweets)
+ ScholarLed [ScholarLed] (83 tweets)

#### Hashtags

Using `tags.py` from twarc utility, I was able to see other hashtags used in the dataset.

```
utils/tags.py deduped.jsonl > deduped-tags.txt
cat deduped-tags.txt | wc -l
#2604
head deduped-tags.txt
```

+ openaccess (5514 tweets)
+ oaweek (5510 tweets)
+ openaccessweek (4753 tweets)
+ oaweek2019 (3131 tweets)
+ oaweek19 (2630 tweets)
+ openaccessweek2019 (2163 tweets)
+ openscience (979 tweets)
+ oa (934 tweets)
+ openforwhom (466 tweets)
+ accessoabierto (449 tweets)

#### URLs

Using `urls.py` from twarc utility, I was able to see URLs tweeted in the dataset.

```
utils/urls.py deduped-unshortened.jsonl > deduped-unshortened-urls.txt
cat deduped-unshortened-urls.txt | sort | uniq -c | sort -n > deduped-unshortened-urls-uniq.txt
cat deduped-unshortened-urls.txt | wc -l
# 7504
cat deduped-unshortened-urls-uniq.txt | wc -l
# 4221
tail deduped-unshortened-urls-uniq.txt
```

+ <a href="https://unpaywall.org/journals">https://unpaywall.org/journals</a> (82 tweets)
+ <a href="http://www.openaccessweek.org/">http://www.openaccessweek.org/</a> (70 tweets)
+ <a href="https://royalsociety.org/journals/">https://royalsociety.org/journals/</a> (44 tweets)
+ <a href="https://royalsocietypublishing.org/doi/10.1098/rspb.2019.2025">https://royalsocietypublishing.org/doi/10.1098/rspb.2019.2025</a> (33 tweets)
+ <a href="https://es-la.facebook.com/UdeArroba/videos/semana-del-acceso-abierto-conferencia-virtual-fernanda-pesset/447541442784653/">https://es-la.facebook.com/UdeArroba/videos/semana-del-acceso-abierto-conferencia-virtual-fernanda-pesset/447541442784653/</a> (33 tweets)

#### Embedded images for URLs

The original article used `image_urls.py` which is no longer available and replaced by `media_url.py`.

```
utils/media_urls.py deduped.jsonl > deduped-images.txt
cat deduped-images.txt | sort | uniq -c | sort -n > deduped-images-uniq.txt
cat deduped-images.txt | wc -l
#4942
cat deduped-images-uniq.txt | wc -l
#4827
tail deduped-images-uniq.txt
```

**Image**
![OA image](/oa_image.jpg)

#### Emojis

The original article didn't explain the emoji, but I found that twarc provides `emojis.py` so I just tried for fun.

```
utils/emojis.py deduped.jsonl > deduped-emoji.txt
```

**Emojis**
![Emojis](/emojis.png)

### 4. Next steps

I wish I knew this tool earlier and there was dedicated staff who was responsible for digital preservation at my institution. Nonetheless, I learned several tools (i.e., <a href="https://gwu-libraries.github.io/sfm-ui/">Social Feed Manager</a>) from the digital preservation community (#digipres) so I will try it to learn by doing and do my best to convince other people that this is important and should be one of our responsibilities. I also discovered one research done by Anthony T. Pinter and Ben Goldman - <a href="https://journal.code4lib.org/articles/12676">Recount: Revisiting the 42nd Canadian Federal Election to Evaluate the Efficacy of Retroactive Tweet Collection</a> to play Twitter beyond its 7 days limits. I am not an expert, but I do believe that this is important. It could be small contribution, but I'd like to improve myself to contribute even small to the community.

P.S. - I uploaded <a href="https://figshare.com/articles/openaccessweek-2019-tweet-ids_txt/10269650">dehydrated tweet IDs</a> to figshare if you want to reproduce this research or replicate with your own dataset.
