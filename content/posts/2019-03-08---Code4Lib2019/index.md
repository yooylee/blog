---
title: "What I learned from Code4Lib 2019"
date: "2019-03-07"
template: "post"
draft: false
slug: "/posts/what-i-learned-from-code4lib2019"
category: "Conferences"
tags:
  - "Conferences"
  - "Code4Lib"
  - "Professional development"

description: "I attended the Code4Lib 2019 and this posting is about what I learned from the conference, especially on digital curation and preservation. There were amazing presentations on machine learning, accessibility, and etc., but I would like to reflect on this topic as this is one of my current projects at uOttawa Library."
socialImage: "./RStudio-Project.jpg"

---

It has been already almost two weeks since I was back from the Code4Lib 2019 conference. Since I was selected as one of the Diversity Scholarships recipients in 2017, I have tried to attend the Code4Lib conferences and be involved in the community. Code4Lib is one of my favorite conferences for its quality and community and this year was really amazing. I learned a lot and met a great group of people. Then, I would like to briefly reflect on the Code4Lib 2019 conference.

## Digital curation and preservation

These days I have been working with my colleague, Marina Bokovay (Head, Archives and Special Collections) on digital curation and preservation at my current institution. My focus has been on “Access” and “User Experience” - how users can easily find what they want or how users can access materials without any difficulty. Frankly, I have never thought seriously about long-term preservation. Working with her, I grasped the importance of preservation, concepts (AIP, DIP, SIP), and tools (Archivematica). Because digital curation and preservation are in a very early stage at my institution, I took <a href="https://docs.google.com/presentation/d/11Ug8Z9BJ_sS-pQcdPmM96BMXBrpho2ASRp0pcZIIbpE/edit?usp=sharing">the Forensic Files workshop</a> offered by Sara Allain and Ashley Blewer from <a href="https://www.artefactual.com/">Artefactual</a>.

When I was a student in Korea, I used <a href="https://bit.ly/2EKviFI">Hangul</a> as a main word processor and all of my files were produced in this system. I moved to Canada and bought a new laptop and then I was no longer able to open my .hwp files stored in my external device as I didn’t buy its license to install it. I googled and found solutions that I could open them either in OpenOffice or LibreOffice but my issue was that the files were corrupted during this conversion process. However, because it was my personal work files (who may want to see my school papers), I didn’t think about how this could be challenges for digital curation and preservation (Now I know this!).

Therefore, Ashley’s explanation on files, formats, and registries were really helpful for me (as a beginner) to understand overview concepts. There are registries that we can check like <a href="http://www.nationalarchives.gov.uk/PRONOM/Default.aspx">PRONOM</a> and <a href="https://www.loc.gov/preservation/digital/formats/fdd/browse_list.shtml">Format Descriptions</a>. During the workshop, I also learned what <a href="https://twitter.com/realAdrianBrown/status/1097960463483187200">PRONOM stands for</a> ;) There are different types of file format signatures: external like filename extensions (.hwp, .pdf) , internal (byte sequences), and container (.zip). With a hex editor, one of my text files was displayed in their hexadecimal values. I learned that I could examine individual bytes of each file and identify patterns or byte sequences in order to detect its signature by comparing with other files of the same format. Moreover, she showed us different tools for file analysis like FIDO, Siegfried, and JHOVE to do that work for us instead of manually verifying with a hex editors. These tools analyze files, report issues, and identify file formats for us.

In the afternoon workshop, Sara went through a life cycle of digital preservation (Accessioning and curation - Digitization - Characterization - Metadata extraction - Normalization - Derivative generation - Presentation). There should be decisions made in each step and the digital curation and preservation are neither a starting point nor an ending point to manage born-digital or digitized materials. It is really one part of the entire cohesive process. There was also an in-depth discussion about embedded metadata vs. separate it from the file, what format should be in a preservation format, and how to collect descriptive metadata (not just technical metadata). Then, she demonstrated us how Archivematica worked. My institution recently subscribed to the <a href="https://permafrost.scholarsportal.info/">Scholars Portal’s Permafrost service</a> where it provides hosted Archivematica and <a href="https://cloud.scholarsportal.info/">OLRC’s storage</a>, so her demonstration was really useful for me. She explained to us how Archivematica uses multiple open source tools that we learned in the morning session such as ExifTool, FIDO, and JHOVE towards digital preservation workflow.

I also liked Ilya Kreymer’s presentation on *Webrecorder: Developing an open-source high-fidelity web archiving toolset*. One of my first projects at uOttawa was the NAHO (National Aboriginal Health Organization) website archiving project from which I learned how difficult this could be to properly archive dynamic content or user-driven action content. <a href="https://webrecorder.io">Webrecorder</a> is based on the ISO standard WARC file format and it allows users to easily archive JS content. He also insisted that web archiving isn’t archiving the entire web which I didn’t really thought before the NAHO web archiving project.

Stefana Breitwieser from Canadian Centre for Architecture also did an amazing lighting talk on *SCOPE: a born digital access interface*. The SCOPE (<a href="https://journal.code4lib.org/articles/14283">Code4Lib Article</a> | <a href="https://github.com/CCA-Public/dip-access-interface">Github repo</a>) is a tool which enables users to easily access and search DIPs. She said that the SCOPE is available in their reading room for their users and I would like to explore more about this once there are DIPs at our institution and differences between AtoM and SCOPE.

Since I was new to digital curation and preservation, I didn’t know really anyone. But after Code4Lib 2019, I feel a bit connected to the community. I had a chance to interact with archivists, preservation librarians, and developers. It was also good to meet people in-person whom you knew via community work but never met before. I am still observing a lot of concepts and tools, but I am really glad to attend the Code4Lib 2019 conference and learn from amazing people.
