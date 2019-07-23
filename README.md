# Course-articles-videos-recommendation
This is a project in which we are trying to create an algorithm that can recommend (articles, courses, &amp; video) based on your professional needs, by scraping indeed job entries and determining  (trough NLP/NER) skills convenable to that need, filling it by determining skills provided by the online courses and articles or videos to recommend it to you.
# First, we collect the data 
## Stationary or dynamic
With stationary data our agent will become less and less relevant with time passing by, in other words he will get old and start recommending for example courses of HTML5 in 2050 while there is no one use of it anymore!!!
Therefore, our algorithm is aiming to automatically  collect the data sources from internet to keep its dataset relevant! and be a little more accurate by having the possibility to control the data structure! 
That will be possible by creating a web scraping algorithm, I was here inspired by  - George Liu's - article "Scraping Job Posting Data from Indeed using Selenium and BeautifulSoup" : https://towardsdatascience.com/scraping-job-posting-data-from-indeed-using-selenium-and-beautifulsoup-dfc86230baac  
his GitHub repository : https://github.com/georgeliu1998/ideal_profiles/blob/master/scrape_data.py?source=post_page---------------------------
Though it wasn't a copy/past situation, since it needed some modification cause its outdated and the fact that indeed is constantly updating their website, so the working web scraper of today will not necessary work tomorrow, but its will if you change 3 to 2 lines of code! That wasn't the case any way, I have changed every function to make the code work the way I wanted it ! but the structure is pretty much the same :), for more info check out : https://github.com/ZA3karia/course-articles-videos-recomendation/blob/master/webscarping_indeed_jobs.md
 
 
# NER on our data
## state-of-the-art
In the first time I intended to use state-of-the-art Named entity recognition, to get the best accuracy possible, so I went using Flair framework [you can find their tutorials here : https://github.com/zalandoresearch/flair/blob/master/resources/docs/TUTORIAL_1_BASICS.md]
But they were not as accurate as I wanted them to be, neither as fast as feasible for my case, the algorithm was well rated, but it wasn't dedicated to work on my type of dataset,& it wass very expensive in terms of hardware consumption, up to 1h for their 'ner-fast' model to predict keywords on my data ! I had to re train it to get the best of accuracy but I have no training data, and even if I had it, 1hour predicting is pretty rough, exactly if I am using a dynamic agent!! 
## Old but Gold
Therefor as much as I wanted to use state of the art algorithms, I went back in time to use a very basic and cheap in hardware consumption algorithm, "IDF calculations"
And my work was mainly based on the work of - Sowmya Vivek's - article :https://medium.com/analytics-vidhya/automated-keyword-extraction-from-articles-using-nlp-bfd864f41b34
for more details check out my notebook :https://github.com/ZA3karia/course-articles-videos-recomendation/blob/master/treating_indeed_dataset.ipynb


