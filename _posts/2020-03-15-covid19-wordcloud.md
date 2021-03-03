---
layout: post
title: "COVID-19 Twitter Word Cloud"
subtitle: "Twitter Analytics using R Stats"
date: 2020-03-15
background: ' '
---

The COVID-19 pandemic has significantly increased the need for data analysis, done by many professionals around the world. Some might even say that [data visualization is experiencing a breakthrough moment](https://medium.com/nightingale/data-visualizations-breakthrough-moment-in-the-covid-19-crisis-ce46627c7db5) during this crisis.

Interestingly, the majority of the analysis done about the pandemic has been centered around the evolution of confirmed cases, deaths, and recovery rates around the world. Examples like the [COVID-19 ArcGIS Dashboard by the CSSE at Johns Hopkins University](https://gisanddata.maps.arcgis.com/apps/opsdashboard/index.html#/bda7594740fd40299423467b48e9ecf6) are the most notable data visualizations being used around the world to keep track of case statistics.

While getting informed about the pandemic and looking at different visualizations shared on Twitter, I got very interested in learning more about what Twitter users around the world were tweeting in relation to the COVID-19 pandemic. This led me to start this quarantine project to do some text analytics on Twitter using R, the rtweet package, and the Twitter API.

<br>
# Set up
<hr/>
This analysis was done using the [rtweet](https://github.com/ropensci/rtweet) R package while following a great tutorial by Laura Ellis (a.k.a. [LittleMissData](https://www.littlemissdata.com/)), which you can find here: [Awesome Twitter Word Cloud in R](https://www.littlemissdata.com/blog/wordclouds?rq=wordcloud)

You can follow this tutorial using your local installation of [R Studio](https://rstudio.com/) or you can use a free, hosted, multi-language collaboration environment like [IBM Watson Studio](https://www.ibm.com/cloud/watson-studio). If you'd like to get started with R in IBM Watson Studio, I'd recommend this great tutorial (also by Laura Ellis): [Get Started with R (For Free) in IBM Watson Studio](https://www.littlemissdata.com/blog/watsonstudio)

<br>
# Analysis
<hr/>
Once I got my word cloud R script working on my IBM Watson Studio Environment, it was time to start analyzing tweets from topics related to the COVID-19 pandemic. The easiest way to find related tweets was to search by hashtags.


#### Fun Fact 💡
Did you know that, according to [Wikipedia](https://en.wikipedia.org/wiki/Hashtag), the use of hashtags was first proposed by [Chris Messina](https://en.wikipedia.org/wiki/Chris_Messina_(open-source_advocate)) in a 2007 tweet, that, altough initially decried by Twitter as a "thing for nerds", eventually led to their use rapdily becoming widespread throughout the platform. Messina, who made no attempt to patent the use because he felt *"they were born of the internet, and owned by no one"*, has subsequently been credited as the godfather of the hashtag.


## #coronavirus
For this analysis, I used a sample of 5000 tweets including the hashtag #coronavirus.

<img class="img-fluid" src="/img/posts/cloud1.jpeg" alt="Word Cloud Screenshot"/>

As you can see from the word cloud above, it is important to remove redundant and dominant values (like the word *coronavirus*, in this example) to better analyze the word cloud. After removing these values, the new word cloud looked like this:

<img class="img-fluid" src="/img/posts/cloud2.jpeg" alt="Word Cloud Screenshot"/>

## Observations
Here are a few observations I had after analyzing the results:
* Although I removed stop words (i.e. commonly-used words like "the", "of", etc.), I forgot to filter out stopwords in different languages (like "lo", "si", "von", etc.). After doing some research, I found that [rtweet supports stop words in multiple languages](https://docs.ropensci.org/rtweet/reference/stopwordslangs.html).
* It's interesting to see the political influence around this particular subject by looking at the presence of words like *realdonaldtrump*, *askdoctortrump*, and *borisjohnson*.
* This sample was taken on March 15th 2020, right when most countries around the world were entering an extended lockdown period and promoting the need for social distancing, as shown by the presence of words like *staythefhome*, *stayathome*, *restezchezvous*, *socialdistancing*, *cuarentena*, *mequedoencasa*, etc.
* Due to the quarantine measures around the world, some countries experienced a surge in panic shopping (as shown by the presence of the word *panicshopping*). This can be verified using [the Google Trends search](https://trends.google.com/trends/explore?date=2020-01-01%202020-05-31&q=panic%20shopping) below, showing a spike in Google Searches around the weekend of March 15th 2020.

<script type="text/javascript" src="https://ssl.gstatic.com/trends_nrtr/2213_RC01/embed_loader.js"></script> <script type="text/javascript"> trends.embed.renderExploreWidget("TIMESERIES", {"comparisonItem":[{"keyword":"panic shopping","geo":"","time":"2020-01-01 2020-05-31"}],"category":0,"property":""}, {"exploreQuery":"date=2020-01-01%202020-05-31&q=panic%20shopping","guestPath":"https://trends.google.com:443/trends/embed/"}); </script> 

<br>
# Data & Resources
<hr/>
As mentioned before, the majority of the data analysis performed to date on the topic of COVID-19 has been done around case statistics. As pointed by Laura Ellis on Twitter, this is thanks to all the data heroes around who are working to make all the case data available and accessible to everyone.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">This is the first twitter analysis I’ve seen on <a href="https://twitter.com/hashtag/COVID19?src=hash&amp;ref_src=twsrc%5Etfw">#COVID19</a> <br><br>It strikes me this is bc the focus has been on analyzing case stats. <br><br> 🦸🏻‍♀️ 🦸‍♂️ And this is bc of the <a href="https://twitter.com/hashtag/data?src=hash&amp;ref_src=twsrc%5Etfw">#data</a> heroes who have made the case data so available and accessible. <a href="https://t.co/MHE9JguCbd">https://t.co/MHE9JguCbd</a></p>&mdash; Laura Ellis (@LittleMissData) <a href="https://twitter.com/LittleMissData/status/1239347783569739778?ref_src=twsrc%5Etfw">March 16, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

Here's a list of the datasets and resources shared in the thread above, if you're interested in doing further analysis:
* nCovid2019 R package by [@guangchuangyu](https://twitter.com/guangchuangyu): https://github.com/GuangchuangYu/nCov2019
* Coronavirus R package by [@ramikrispin](https://twitter.com/ramikrispin): https://github.com/RamiKrispin/coronavirus
* Covid Python package by Johns Hopkins University: https://pypi.org/project/covid/
* Covidify Python package by [Aaron Ward](https://github.com/AaronWard): https://github.com/AaronWard/covidify

And a lot more resources being shared on Twitter with the hashtag [#OpenData](https://twitter.com/hashtag/OpenData).

*Special thanks to Laura Ellis [(@LittleMissData)](https://twitter.com/LittleMissData) for sharing her knowledge and creating the tutorials that made this analysis possible.*
