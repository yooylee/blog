---
title: "Exploring AI in Metadata and Cataloguing"
date: "2026-01-21"
template: "post"
draft: false
slug: "/posts/ai-in-the-metadata-and-cataloguing"
category: "General"
tags:
  - "AI"
  - "ML"
  - "Metadata"
  - "Cataloguing"

description: "This post shares the presentation script I delivered to the Library Council at my institution on January 21, 2026, where I outlined the work my team has been doing around AI, metadata, and cataloguing."

socialImage: "./image.jpg"
---

You can find my <a href="https://doi.org/10.5281/zenodo.18459070">presentation slides</a>.

### Page 1: Introduction

*Hello everyone,
Thank you so much for giving me the opportunity to talk about metadata and cataloguing work.
When I returned to this role after my leave, I was a little surprised to realize that many people didn’t quite know what we do, beyond a general sense of “oh, cataloguing.”
That made me reflect on my role as Head of the Metadata and Cataloguing team, and on the importance of sharing more about our work so you can have a better picture of what we do.
If you need any help with cataloguing or metadata for any type of project, my team is here for you, and we would really welcome those conversations. 
So today, I want to share some exploratory examples of how we are using AI, more specifically, machine learning in our work.*

### Page 2: My journey to AI/ML

*These days, I am reading a book called Research is Ceremony which is Indigenous research method recommended by a colleague from University of Toronto and one way I wanted to incorporate was to think about my relationship.
I’d like to start by sharing my personal journey with AI and ML.
Any of you remembered the AlphaGo versus Lee Sedol match back in 2016?
That was my first real exposure to AI and I remember being genuinely shocked, not just because AlphaGo won four out of five games, but because of how beautifully it played, it ways I had never seen before. 
I became really curious about what was behind it, so I took some courses on neural networks. At the time, though, everything felt very technical, and no one really knew what AI would become, how it could be used, or what was happening behind the scenes to produce something so beautiful.*

### Page 3: My journey to AI/ML

*In addition, this quote from Lee Sedol really made me reflect on how roles change with the introduction of AI, although back in 2016, I had no way of knowing that this shift would actually happen.*

### Page 4: Generative AI

*Then ChatGPT was introduced in 2022, around the time my daughter was born, thanks to Allison, who told me about it.
In Korea, it quickly became hugely popular. Even my parents started using it before I did, generating all kinds of art and other creative things.
To be honest, I didn’t really pay much attention at the time. I had a tiny human being who needed constant care, not artificial intelligence at all lol
After I returned from my leave, though, I was inspired by Majela’s presentation on generative AI and instruction, and everyone was talking about AI, AI, and AI!
So I decided to go back to my notes from 2016 and revisit them in light of today’s open AI models. This felt very different from what was possible back then and it seemed like the right time to explore again.
My supervisor, Liz, also encouraged me to experiment and test ideas even if some of them might fail.
That’s the relationship that I had with AI and ML, very open and curious.*

### Page 5: Considerations

*When I started looking for test cases, we didn’t yet have the guiding principles we have now, so I relied on a few personal considerations.
First, I looked for something that was important, but not quite a priority, so it hadn’t been explored yet.
Second, I chose something that would be practically impossible to do manually because of the sheer number of records involved.
And third, I wanted something that was simply fun to explore. Thinking about environment impact, I don’t want to waste that much.
I didn’t want to interfere with anything that was already working well, so I intentionally focused on areas where experimentation felt low-risk but meaningful.*

### Page 6: Old theses

*A perfect example is a test case focused on enhancing metadata for older theses. This idea actually came from Catherine McGovern, who pointed out that there was no easy way to know how many French records we have in our institutional repository. 
In many of our older records, there was no metadata policy in place at the time, so that information was simply never recorded.
When I looked into the older theses collection, I found that there was very little metadata beyond the title and author. That made it a particularly interesting—and fun—area to explore.
I used secure servers provided by the Digital Research Alliance of Canada which is amazing and Jarno's help was very exceptional to set up and did not use free AI models that could train on our data. 
The first use case focused on identifying the written language of documents and implementing quality assurance checks. The results were over 95% accurate, with an error rate of under 5%, which was encouraging.*

### Page 7: Old theses

*The next step will be to explore extracting additional tyes of metadata such as abstracts, keywords, and department or school information to further enhance our metadata.*

### Page 8: SciFree subjects translation

*Leigh-Ann and Yohann approached me about this interesting project. As a bilingual institution, we have a mandate to provide a bilingual interface. In practice, however, many vendors supply metadata only in English. One example is subject headings, which are often provided exclusively in English.
Manually translating these subjects into French would be daunting at scale. To address this, we used the DeepL Pro API paid one(rather than the free version, which can be used to train models). The results were promising.*

### Page 9: Alma AI metadata assistant

*We tested this approach in 2025, but the consensus at the time was that it was not ready for production use, particularly for French cataloguing. However, some elements such as subject headings and call numbers performed reasonably well.
We plan to test the tool again, but with a more targeted approach. Last year, we applied it across all fields, which resulted in significant redundancy. This time, we will focus on specific fields and on original cataloguing workflows in particular.
Since most of our current work is copy cataloguing, the impact there is likely to be limited, but this new focus will allow us to better assess where the tool can meaningfully support original cataloguing work.*

### Summary

I shared how the Metadata and Cataloguing team has been experimenting with AI to support metadata and cataloguing work. The examples focused on practical and limited use cases such as language identification, bilingual metadata enhancement, and targeted testing of AI-assisted tools. Rather than positioning AI as a replacement for professional judgement, this work explored where it can meaningfully support existing workflows while acknowledging current limitations and risks.












