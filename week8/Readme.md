# Week 8
Your first task is to learn basic python and a web scraping framework named Scrapy. First, focus on python, I will have the tutorial for Scrapy ready by evening. Anyways, if you know python, you can search Scrapy on YouTube and see a video by John Watson Rooney. The tutorial will be from that video. You can refer to any other resource also. As for python, I can tell resources but everyone likes to learn in their own way. So I guess you should find your own calling. 

I will give you two days for basic stuff and then you can try to understand the codebase of Scrapy after cloning from GitHub. I will prepare a tutorial for that also and that will be out in two days at max. This week's assignment will majorly comprise explaining the codebase in a report and maybe one small task. But don't lack out, your explanation should be good enough such that if I tell you to make easy changes such that the output becomes this or the input is this or automate for a particular form of website, then you should be able to do it.

For those who have lost marks in the previous assignments, if the performance is satisfactory, we may give some bonus to you regarding completion of SoC but I will talk to other mentors and these details will not be revealed until the end so try to give your best. 

Happy Learning

[ScraPy Docs](https://docs.scrapy.org/en/latest/intro/tutorial.html)
## Continuation
Since we have only one week left in the SoC, instead of understanding how scrapy code is written, just understand how it works, which is mentioned in detail in the documentation - I want you to build a web crawler which creates sitemaps. Mostly it is the opposite that the crawlers use sitemaps to navigate but sitemaps are not always available to us. So, what your crawler should do is given a set of starting urls and a prescribed depth of recursion, it should initialize a graph data structure and create nodes for the start urls and parse their html files for the href tag. during this process, there may be repetitions, you will have to deal with them, and this should go only till a prescribed depth of recursion, if depth is 3, link1->link2->link3->stop.
