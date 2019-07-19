# course-articles-videos-recomendation
this is a project in witch we are tiying to creat an algorithm that can recomande (articles, courses, &amp; video) based on your profeetional needs, by scaring indeed job entries and determinings (trough NLP/NER) skills convenable to that need, filling it by determining skills provided by the online courses and articls or videos to recomande it to you
# first we collect the data 
## stationary or dynamic
with stationary data our agent will become less and less relative with time passing by, in other words he will get old and start recomending for examplescourses of HTML5 in 2050 while no one use it any more !!!
therefore our algorithm is aiming to automaticly collect the data sources from internet to keep its dataset relevent! and be a little more accurate by having a the possibility to controll the data structure! 
that will be possible by creating a web scraping algorithm, I was here inspired by  George Liu's article "Scraping Job Posting Data from Indeed using Selenium and BeautifulSoup" : https://towardsdatascience.com/scraping-job-posting-data-from-indeed-using-selenium-and-beautifulsoup-dfc86230baac
his github repository : https://github.com/georgeliu1998/ideal_profiles/blob/master/scrape_data.py?source=post_page---------------------------
 Though it wasen't a copy/past situation, since it needed some modification cause its outdated and the fact that indeed is constantly updating theire website, so the working project of today will not necessartly work tomorow, but its will if you change 3 to 2 lines of code! That wasent hte cas any way, I have changed every function to make the code work the way I wanted it ! but the structure is pretty much the same :), for more info check out : https://github.com/ZA3karia/course-articles-videos-recomendation/blob/master/webscarping_indeed_jobs.md
 
 
 #NER on our data
