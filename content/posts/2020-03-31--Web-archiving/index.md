---
title: "Covid-19 Web Archiving at uOttawa"
date: "2020-04-08"
template: "post"
draft: false
slug: "/posts/covid-19-web-archiving-at-uottawa"
category: "Web archiving"
tags:
  - "Web archiving"
  - "Twitter archiving"
  - "Content"
  - "Preservation"

description: "This blog post is about my journey to capture websites and tweets in Twitter around the Covid-19 pandemic mostly at uOttawa but few in the capital region."

socialImage: "./image.jpg"
---

*Disclaimer: I do believe the importance of web archiving, but it is neither my full-time job nor my responsibility at work. As a librarian who believes in open access, open scholarship, and digital preservation, I am learning tools and techniques constantly to do my best.*

After my very first web archiving project at uOttawa to preserve the <a href="https://archive-it.org/collections/9444">digital NAHO (National Aboriginal Health Organization) content</a> before permanently disappearing from the Internet, I had thought about how to promote our web archiving initiative to get permission from website owners as well as where to find unique and niche content that our library could only preserve. I've learned from my UX studies that users consider collections as one of the most important library's mission. One of the most visited web pages is always **resources** including subscribed databases and digital collections. I also learned from my colleagues at IUPUI the importance to digitize <a href="https://ulib.iupui.edu/collections">unique collections</a> around Indianapolis and Midwest in collaboration with local partners and faculty. The scope of web archiving initiative as a collection could start from local yet unique stories that big institutions could miss to record.

### Living archive

I learned the concept of 'living archive' from <a href=" https://doi.org/10.1080/13614576.2015.1114839">Rollason-Cass & Reed (2015)</a> while doing my pilot project to document racial discrimination on campus. The living archive is an event-based web archiving project or a collection developed around a spontaneous event to capture web content while it occurs (e.g., <a href="https://archive-it.org/home/IAGlobalEvents">Internet Archive Global Events</a>). Many studies insist the fragility of digital information and provide various guidelines and best practices to preserve massive web information before it disappears (Davis, 2014; Dowling, 2019; Khan & Rahman, 2019; Milligan, Ruest, & St.Onge, 2016; Niu, 2012; Pennock, 2013; UK National Archives, 2011). Rollason-Cass and Reed (2015) found that only 41% of websites archived during the Occupy Wall Street movement in 2011-2012 were still available in 2014.

<a href="https://www.dpconline.org/blog/series-wa-coronavirus-sdthomson-2">Thomson (2020)</a> shares recently collaborative national and global initiatives to archive much of the pandemic content as online information changes so quickly and there is new information generated daily. There is also a <a href="https://docs.google.com/document/d/1v5tso8spFq6SpW53h2OJULcdRoPEbyI6xpah31kW-H0/edit">list of the active documentation projects</a> for the COVID-19. Since the outbreak started in Ottawa around mid-March, the University of Ottawa created a <a href="https://www.uottawa.ca/coronavirus/en">dedicated web page</a> regarding COVID-19 and I noticed that its main part was designed to be updated regularly with new information. So I took the first step to preserve how <a href="https://archive-it.org/collections/13646">uOttawa</a> (link: our collection on Archive-It) responds to the pandemic with Archive-It and how we react to it in Twitter with <a href="https://github.com/DocNow/twarc">twarc</a> (`#coronavirus and #ottawa`, `#covid19canada and #ottawa`, `#çavabienaller`, and `#CERB`).

### Seed selection

There are many challenges around web archiving in general like technical issues, privacy, copyright, access, and etc., but I think that there are even more when it comes to preservation of online content in the spontaneous event model. The most challenging part is to **decide** what to preserve among so much content produced every day given limited resources. Khan and Rahman (2019) summarizes different ways to define the scope of web archive: site-centric to focus on a particular website, topic-centric to preserve information on a particular topic, and domain-specific like `.com`, `.edu`, and `.ca`. Since the pandemic is around topic-based, as Niu (2012) mentions, human judgment is involved to select what to archive. This manual selection is time-consuming and expensive. That's why many event-based web archiving initiatives are done with a varied crowdsourced approach to curation. The <a href="http://netpreserve.org/">International Internet Preservation Consortium (IIPC)</a> asks for <a href="https://netpreserveblog.wordpress.com/2020/02/13/cdg-collection-novel-coronavirus/">help</a> to nominate websites regarding Covid-19 and its <a href="https://archive-it.org/collections/13529">collection</a> is publicly available.

Like many other institutions, web archiving is done by a small group of team members and there is no difference at uOttawa. Dealing with a global event, but my approach was to focus on local stories that national libraries could miss, but one person could handle - so I started from uOttawa and library content, uOttawa student newspapers, social media, and municipal websites. In addition, as Thomson (2020) points out, we would miss lots of voices if we just archived only official channels like institution websites, but archiving social media content is not easy. For example, in order to archive Facebook group discussion, you need permission first and it is obviously needed but very challenging to deal with time-sensitive information. I also learned how hard it is to archive visual-audio content using a crawl with Archive-It. It is not comprehensive, but there are many open source tools developed to archive Twitter content so I started with `#coronavirus and #ottawa` and `#covid19canada and #ottawa` Twitter hashtags and add more along the way.

### Tools

My institution has an institutional Archive-It account through <a href="http://blog.archive.org/2017/08/02/canadian-library-consortia-ocul-and-coppul-join-forces-with-archive-it-to-expand-web-archiving-in-canada/">OCUL (Ontario Council of University Libraries)</a> since 2017 so Archive-It is a main tool to archive most of the websites. In terms of Twitter content, I ran twarc commands to collect tweets with hashtags `#coronavirus and #ottawa` and `#covid19canada and #ottawa` since March 13 on my local machine first. The first combination of hashtags generated almost 44 GB datasets for 7 days so I ran out of memory. Then, I scheduled different jobs with the twarc commands in the <a href="https://www.computecanada.ca/">Compute Canada environment</a>. There are <a href="https://github.com/iipc/awesome-web-archiving">many other tools</a> available too.

### Next steps

In the last two weeks, I mainly focused on acquisition and selection not to miss any constantly changing content. In the <a href="https://archive-it.org/blog/learn-more/publications/web-archiving-life-cycle-model/">web archiving lifecycle model</a> (Bragg and Hanna, 2013), it is just a start though. Davis (2014) describes well-known technical issues like difficulty of archiving dynamic content, so it is an important step to verify quality of the crawls. I also would like to learn more about metadata to describe archived web content. Niu (2012) argues the metadata generation depends on the scale of the web archive and available resources. Since it is a small project compared to other national initiatives, I would like to enhance its description including not only descriptive metadata but also technical metadata. Lastly, I would like to release a WARC file for computational access so that researchers could analyze it in their preferred tools.

### References
+ Bragg, M, & Hanna, K. (2013). Web Archiving Lifecycle Model. Retrieved from https://archive-it.org/blog/learn-more/publications/web-archiving-life-cycle-model/

+ Davis, C. (2014). Archiving the Web: A Case Study from the University of Victoria. The Code4Lib Journal, 26. https://journal.code4lib.org/articles/10015

+ Dowling, S. (2019). Why there’s so little left of the early internet. Retrieved October 30, 2019, from https://www.bbc.com/future/article/20190401-why-theres-so-little-left-of-the-early-internet

+ Khan, M., & Rahman, A. U. (2019). A Systematic Approach Towards Web Preservation. Information Technology and Libraries, 38(1), 71–90. https://doi.org/10.6017/ital.v38i1.10181

+ Milligan, I., Ruest, N., & St.Onge, A. (2016). The great WARC adventure: Using SIPS, AIPS, and DIPS to document SLAPPs. Digital Studies/Le Champ Numérique. https://doi.org/10.16995/dscn.18

+ Niu, J. (2012). An Overview of Web Archiving. D-Lib Magazine, 18(3/4). https://doi.org/10.1045/march2012-niu1

+ Pennock, M. (2013). Web-Archiving. Digital Preservation Coalition. https://doi.org/10.7207/twr13-01

+ Rollason-Cass, S., & Reed, S. (2015). Living Movements, Living Archives: Selecting and Archiving Web Content During Times of Social Unrest. New Review of Information Networking, 20(1–2), 241–247. https://doi.org/10.1080/13614576.2015.1114839

+ Thomson, S. D. (2020). Catching an Avalanche with a Teaspoon: The Global Challenge of Web Archiving the Coronavirus Pandemic—Digital Preservation Coalition. Retrieved April 3, 2020, from https://www.dpconline.org/blog/series-wa-coronavirus-sdthomson-2

+ UK National Archives. (2011). Web Archiving Guidance. Retrieved from https://nationalarchives.gov.uk/documents/information-management/web-archiving-guidance.pdf
