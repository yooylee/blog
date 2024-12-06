---
title: "Archives Unleashed Datathon @Washington"
date: "2019-04-12"
template: "post"
draft: false
slug: "/posts/archives-unleashed-datathon-washington"
category: "Datathon"
tags:
  - "Web archiving"
  - "Tools"
description: "I would like to share my participation in the Archives Unleashed Datathon #Washington held from March 21 to March 22, 2019 at the Gelman Library, George Washington University. It was an amazing opportunity for me to learn new tools, consider how to use the Archives Unleashed Toolkit in the curation, and explore how researchers would use web collections to answer their research questions."
socialImage: "./AUT.jpg"
---

*Disclaimer: The whole notion of web archiving is new for me. My very first project to embark on web archiving was done only in 2017. I am currently learning about it and what I am saying in this post would be incorrect or could change along the way I learn. Moreover, I’d like to thank to all organizers (Ian Milligan, Laura Wrubel, Dan Kerchner, Rachel Trent, Robin Delaloye, Nick Ruest, Jimmy Lin, and Samantha Fritz) and all participants.*

I was really lucky to participate in the Archives Unleashed Datathon #Washington from March 21 to March 22, 2019 at the Gelman Library, George Washington University. My very first project at my current institution was to archive the NAHO (National Aboriginal Health Organization) collection, including the <a href="https://wayback.archive-it.org/9444/20171213190306/http://www.naho.ca/">NAHO main website</a>. Honestly, I learned on the way most of the things such as how to effectively run crawls, how to deal with dynamic content, how to conduct QA processes, and etc. (I probably sent a lot of emails to Archive-It archivists to ask for their help.) My involvement with this project enabled me to delve into the importance of preserving heritage content, tools, and processes and I’d like to expand my knowledge and skills in web archiving. My colleague, Marina Bokovay (Head of Archives and Special Collections) shared with me the Datathon event and I submitted my application to learn more about it.

## 1. Archives Unleashed Toolkit (AUT) and Archives Unleashed Cloud (AUC)

Before the Datathon, I had to prepare myself to go through some homework which was to use the <a href="https://archivesunleashed.org/aut/">Archives Unleashed Toolkit (AUT)</a>. AUT is an open-source platform built on Hadoop. It lets you create derivative files from WARC files like plain text extraction, name entity recognition, and etc. as well as analysis on site link structure, image, and Twitter. My favourite part was visualization with <a href="https://voyant-tools.org/">Voyant</a> and <a href="https://gephi.org/">Gephi</a>. I briefly learned about resilient distributed datasets (RDD) from the MOOC course, *“Introduction to Apache Spark and AWS”* with Hathi Trust datasets, but couldn’t write a script from scratch. AUT itself is really cool, but documentation with detailed information is really amazing. It provided scripts with detailed explanation which helped me understand what each line meant and what it did.

I also learned from the Datathon about the Archives Unleashed Cloud. Simply describe, it does what AUT does for you with just a click! You don’t even need to run AUT scripts. I synced my institution’s Archive-It collections and AUC automatically created a network graph, full text derivatives and more. In order to test it out, you have to have an Archive-It account, however. <a href="https://ruebot.net">Nick Ruest</a> said that his team was looking into the development that would enable users to upload their own WARC files in the future.

**AUC with NAHO collection**
![Screenshot of the Archives Unleashed Cloud](/AUT.jpg)

## 2. Jupyter Notebook and Dataframes

At the Datathon, we were about 20 people and divided into small groups based on themes or research questions. I worked with <a href="https://twitter.com/moffattchristie">Christie Moffatt</a> from National Library of Medicine and <a href="https://twitter.com/deantiquate">Anna St.Onge</a> from York University Libraries on the <a href="https://www.schlesinger-metooproject-radcliffe.org/">#metoo collection</a> archived by the Schlesinger Library on the History of Women in America at Harvard’s Radcliffe Institute for Advanced Study, seeking for how we could use AUT from a curation/documentation perspective. I was really lucky to collaborate with them as they already had deep knowledge in it.

I did think that the wayback machine could be enough in terms of access. Everyone loves it and I love it too. It’s easy to use and it allows rendering web pages as they were. However, while I prepared the Datathon, access points via the wayback machine only couldn’t be enough. Some researchers may want to explore the raw data in a computational format and analyze datasets using other tools like Python or R.

Just right before the Datathon, the Archives Unleashed project team announced their recent project on <a href="https://news.archivesunleashed.org/exploring-web-archival-data-through-archives-unleashed-cloud-jupyter-notebooks-7605c6ca2b33">Jupyter Notebook</a>. I am familiar with a concept of dataframe (as a R user) and since two years ago, I have been dedicated myself to learn more about Python and Jupyter Notebook, so I’d like to explore more about it. In addition, my team was interested in terms of how this could be used either to promote our collections or document the processes we have done. We believed that this would be great for reproducible research or workflow around web archiving.

What I did first was to convert datasets to dataframe using Python library, <a href="https://pandas.pydata.org/">pandas</a>. My focus was on the content side like what content was captured. What I learned from my very humble web archiving experience was that the web crawl archives not only content but also any elements for visualization and behavior like CSS, Javascript, and etc. Therefore, for the content perspective, I had to remove or filter out some elements which supported for visualization or behavior. Honestly, this is what I did for two days. I didn’t know how to filter out more efficiently or batch remove. I was able to figure out some patterns like “Permanently redirect to..” or “404 Found error”, but since it was a huge dataset, filtering out seemed a never ending story. However, my team figured out where articles/pages were being tweeted as it seemed that there were patterns. As a newbie, I couldn’t complete what I wanted to do at the Datathon, but I’d like to explore more with my institution’s collection in the future.

**Fulltext in the Dataframe**
![Screenshot of the dataframe](/dataframe.jpg)

## 3. Local Preservation and Access to WARC files

The Datathon made me think about how to provide access to WARC files or local WARC file preservation so that researchers themselves could benefit from AUT or AUC in the future. Archive-It provides perpetual preservation plans so when my institution archived the NAHO collection with Archive-It, we didn’t really consider local WARC file preservation. However, since we have <a href="https://permafrost.scholarsportal.info/">the Permafrost service</a> and other tools like BitCurator for our preservation, it could be worth going through preservation locally as well. In addition, we could also provide a WARC file as DIP (Dissemination Information Package).

I am working with Marina Bokovay and <a href="http://www.granthurley.ca">Grant Hurley</a> (Digital Preservation Librarian at Scholars Portal) for preservation for our WARC files and in terms of access, I am working with <a href="https://atthetime.ca">Felicity Taylor</a> (E-Research Librarian) and we’re considering to deposit the DIP in <a href="https://dataverse.scholarsportal.info/dataverse.xhmtl">Dataverse</a> as my institution doesn’t have DAMS (Digital Asset Management Systems) for digital collections yet. (We do have <a href="https://biblio.uottawa.ca/atom/">AtoM</a> for finding aids, <a href="https://ruor.uottawa.ca/">DSpace</a> for our institutional repository, and <a href="https://biblio.uottawa.ca/en/omeka">Omeka</a> for exhibit).

Nick showed us <a href="https://archivesunleashed.org/warclight/">Warclight</a> which could be my institution’s discovery layer of web archives in the format of WARC. Since web archiving is new for my institution, there are not many web archiving collections. However, I do believe that this could only grow so it was good to know how other institutions provide its access to WARC files. The nice thing about Warclight among many other features was that I could filter by content types like html, text, image and etc. In addition, Islandora also provides a Web Archive Solution pack and York University uses the <a href="https://digital.library.yorku.ca/yul-232039/web-archives">Islandora system</a> for their web archiving collections.

## 4. What is the next step?

It was really interesting and fun to see how other teams explored their collections as to answer their questions. I really learned a lot from them. They’ve tried something I wasn’t aware like geocoding, non-textual analysis, and advanced way to use Jupyter Notebook. So now after my amazing experience with Datathon, I’d like to go through again with AUT and AUC. My laptop couldn’t handle data intensive work like NER (Name Entity Recognition) so I will ask for a VM in <a href="https://www.computecanada.ca/">Compute Canada</a> and go through AUT there with my institution’s collection. I will also explore my institution’s collections in AUC. Since one of the collections has a huge amount of data in non-textual element, I’d like to explore the way other group did as well. Finally, I’d like to complete what I wanted to do with Jupyter Notebook with a dataframe mindset. Fingers crossed.
