# Course-articles-videos-recommendation
This is a project in which we are trying to create an algorithm that can recommend (articles, courses, &amp; video) based on your professional needs, by scraping indeed job entries and determining (trough NLP/NER) skills convenable to that need, filling it by determining skills provided by the online courses and articles or videos to recommend it to you.
# First, we collect the data 
## Stationary or dynamic
With stationary data our agent will become less and less relevant with time passing by, in other words he will get old and start recommending for example courses of HTML5 in 2050 while there is no one use of it anymore!!!
Therefore, our algorithm is aiming to automatically collect the data sources from internet to keep its dataset relevant! and be a little more accurate by having the possibility to control the data structure! 
That will be possible by creating a web scraping algorithm, I was here inspired by - George Liu's - article "Scraping Job Posting Data from Indeed using Selenium and BeautifulSoup»: https://towardsdatascience.com/scraping-job-posting-data-from-indeed-using-selenium-and-beautifulsoup-dfc86230baac  
his GitHub repository: https://github.com/georgeliu1998/ideal_profiles/blob/master/scrape_data.py?source=post_page---------------------------
Though it wasn't a copy/past situation, since it needed some modification cause its outdated and the fact that indeed is constantly updating their website, so the working web scraper of today will not necessary work tomorrow, but its will if you change 3 to 2 lines of code! That wasn't the case any way, I have changed every function to make the code work the way I wanted it! but the structure is pretty much the same :), for more info check out: https://github.com/ZA3karia/course-articles-videos-recomendation/blob/master/webscarping_indeed_jobs.md
 
 
# NER on our data
## state-of-the-art
In the first time I intended to use state-of-the-art Named entity recognition, to get the best accuracy possible, so I went using Flair framework [you can find their tutorials here: https://github.com/zalandoresearch/flair/blob/master/resources/docs/TUTORIAL_1_BASICS.md]
But they were not as accurate as I wanted them to be, neither as fast as feasible for my case, the algorithm was well rated, but it wasn't dedicated to work on my type of dataset, & it was very expensive in terms of hardware consumption, up to 1h for their 'ner-fast' model to predict keywords on my data! I had to re train it to get the best of accuracy but I have no training data, and even if I had it, 1hour predicting is pretty rough, exactly if I am using a dynamic agent!! 
## Old but Gold
Therefor as much as I wanted to use state of the art algorithms, I went back in time to use a very basic and cheap in hardware consumption algorithm, "IDF calculations"
And my work was mainly based on the work of - Sowmya Vivek's - article: https://medium.com/analytics-vidhya/automated-keyword-extraction-from-articles-using-nlp-bfd864f41b34
for more details check out my notebook: https://github.com/ZA3karia/course-articles-videos-recomendation/blob/master/treating_indeed_dataset.ipynb


#Get that article
##scrap the web again?
Now that we have got the fields that the person is interested in, and we know the up to date terms that are related to him, we need to get the best out of this information, and serve him with the best articles available in the web, therefore the first instinct that came up to my mind was to create another big dynamic dataset that contains every article related to every Field & interest and then recommend them to my user. but this method is not only inconvenient and require a lot of storage but its -impossible-!!!
most articles refused my scraping attempts unfortunately. Yeah, I can use selenium and get the data anyway! but there is a way around this!
##Hi google
The Google custom search engine python REST API is a relief it made it all simple to get every piece of the data I want, and it made all the articles exposed and with a quality reference two!
https://cse.google.com/cse/all
https://medium.com/@hemantjain1999/implementing-web-scraping-in-python-with-beautifulsoup-and-google-api-34c7282b9257
check:              for more info 

#What’s now??
##the easy way....
You can now recommend the articles right away to the user and have a good recommendation system
##the juicy way
But you can also take the Google CSE result and pass it to a classifier and correct it with future recommendations and finish up with a recommender system that updates frequently and personalized to each personnel!

The fact that the second one is a beautiful concept we will do it ;)

#First let’s understand it
##newspaper3k again
In fact, we don’t have to the machine is the one that needs to understand, and we again have the choice either use state-of-the-art algorithms or use an easy framework that doesn’t just give good result but also do the scraping for you (aka: newspaper3k)
for more info check the readme file: 
After that we will have got a good dataset representation of our articles, make in consideration I’ve used a lot of data that It would have been better to know exactly what feature matters, or take it all and apply dimensional reduction, (spoilers: I didn’t, but I will hopefully in the future), now that we got the articles data. We need the target to train the model, unfortunately this data can’t be scrapped NOR predict, because we need to make it relevant to the user, but we can start to be random in the beginning and it will learn as it goes ;)
therefore, I made a Dummy data using Pandas & NumPy you can check the notebook to know how I've done it:
#NN or Classic
Its basically a good choice to use a normal classifier and us
Then I merged the data, I used the Cartesian product then transformed it into a TensorFlow dataset, it would have been better if I 
used Matrices Factorization, but that is for another day.
I then trained a Simple NN using TensorFlow & Keras to recognize the patterns in my data, check my notebook: 

After that you can feed it to your website get the user experience feedback and make your model converge better for every person









