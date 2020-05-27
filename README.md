# UDACITY Data Analysis Nanodegree Project: Data Wrangling - WeRateDogs Twitter archive

## Introduction
Real-world data rarely co mes clean. Using Python and its libraries, I gathered data from a variety of sources and in a variety of formats, assessed its quality and tidiness, then cleaned it. This is called data wrangling. I also documented my wrangling efforts in pdf document Wrangle_report.

The dataset that I wrangled (and analyzed and visualized) is the tweet archive of Twitter user [@dog_rates](https://twitter.com/dog_rates), also known as [WeRateDogs](https://en.wikipedia.org/wiki/WeRateDogs). WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog. These ratings almost always have a denominator of 10. The numerators, though? Almost always greater than 10. 11/10, 12/10, 13/10, etc. Why? Because "they're good dogs Brent."

WeRateDogs [downloaded their Twitter archive](https://help.twitter.com/es/managing-your-account/how-to-download-your-twitter-archive) and sent it to Udacity via email exclusively for you to use in this project. This archive contains basic tweet data (tweet ID, timestamp, text, etc.) for all 5000+ of their tweets as they stood on August 1, 2017. More on this soon.

## Installation
The following packages (libraries) need to be installed. You can install these packages via conda or pip:

- [Python (3.x or higher)](https://www.python.org/downloads/)
- [Jupyter Notebook](https://jupyter.org/)
- [Numpy](https://numpy.org/)
- [Pandas](https://pandas.pydata.org/)
- [Matplotlib](https://matplotlib.org/)
- Requests
- Tweepy
- JSON

Recommended:

[Anaconda](https://www.anaconda.com/distribution/#download-section)

## Project Overview
In this project I investigate the No-show appointments dataset, which collects information from 100k medical appointments in Brazil and is focused on the question of whether or not patients show up for their appointment. A number of characteristics about the patient are included in each row.

Project Table of Contents:
1. Introduction
2. Data Wrangling
3. Exploratory Data Analysis
4. Conclusions
5. Limitations

## The Data

**Enhanced Twitter Archive**

The WeRateDogs Twitter archive contains basic tweet data for all 5000+ of their tweets, but not everything. One column the archive does contain though: each tweet's text, which I used to extract rating, dog name, and dog "stage" (i.e. doggo, floofer, pupper, and puppo) to make this Twitter archive "enhanced." Of the 5000+ tweets, I have filtered for tweets with ratings only (there are 2356).

**Additional Data via the Twitter API**

Back to the basic-ness of Twitter archives: retweet count and favorite count are two of the notable column omissions. Fortunately, this additional data can be gathered by anyone from Twitter's API. Well, "anyone" who has access to data for the 3000 most recent tweets, at least. But I could gather this data for all 5000+. Therefore, I queried Twitter's API to gather this valuable data.

**Image Predictions File**

A Udacity member ran every image in the WeRateDogs Twitter archive through a neural network that can classify breeds of dogs*. The results: a table full of image predictions (the top three only) alongside each tweet ID, image URL, and the image number that corresponded to the most confident prediction (numbered 1 to 4 since tweets can have up to four images).

So for the last row in that table:

 - tweet_id is the last part of the tweet URL after "status/" → https://twitter.com/dog_rates/status/889531135344209921
 - p1 is the algorithm's #1 prediction for the image in the tweet → golden retriever
 - p1_conf is how confident the algorithm is in its #1 prediction → 95%
 - p1_dog is whether or not the #1 prediction is a breed of dog → TRUE
 - p2 is the algorithm's second most likely prediction → Labrador retriever
 - p2_conf is how confident the algorithm is in its #2 prediction → 1%
 - p2_dog is whether or not the #2 prediction is a breed of dog → TRUE
 - etc.

## Files included fot this project: 

1. 2 PDFs reports with the project wrangling and analysis information [Wrangle_report](https://github.com/SaraVicente/Udacity_Project4_Data_Wrangling/blob/master/Wrangle_report.pdf) and [act_report](https://github.com/SaraVicente/Udacity_Project4_Data_Wrangling/blob/master/act_report.pdf)

2. **Python Code** you used to perform the wrangling and the analysis in **(.ipynb format)** [wrangle_act.ipynb](https://github.com/SaraVicente/Udacity_Project4_Data_Wrangling/blob/master/wrangle_act.ipynb)

3. The [twitter-archive-enhanced.csv](https://github.com/SaraVicente/Udacity_Project4_Data_Wrangling/blob/master/twitter-archive-enhanced.csv) with the Data used for the project 

4. A text file ([tweet-json.txt](https://github.com/SaraVicente/Udacity_Project4_Data_Wrangling/blob/master/tweet-json.txt)) with the code for the json data

5. Data for the Image Predictions[image-predictions](https://github.com/SaraVicente/Udacity_Project4_Data_Wrangling/blob/master/image-predictions.tsv)

6. PDF with the [PROJECT RUBRIC](https://github.com/SaraVicente/Udacity_Project4_Data_Wrangling/blob/master/Udacity%20Rubric-Wrangle-Assess.pdf)

## Analysis Questions covered in the project

 - QUESTION 1: ARE THERE ANY VARIABLES CORRELATED WITH EACH OTHER?
 - QUESTION 2: DISTRIBUTION OF FAVORITES, RETWEETS AND RATING OVER TIME?
 - QUESTION 3: WHAT IS THE DISTRIBUTION OF THE NUMBER OF TWEETS OVER TIME?
 - QUESTION 4: WHICH IS THE MOST POPULAR DOG BREED?
 - QUESTION 5: WHAT IS THE MOST POPULAR DOG NAME?
 - QUESTION 6: WHAT IS THE MOST POPULAR DOG STAGE?
 - QUESTION 7: WHICH DOG STAGE HAS THE HIGHEST RATING?
 - QUESTION 8: DO TWEETS WITH GREATER RATING GET MORE RETWEETS AND FAVORITES?
 - QUESTION 9: DO TWEETS GET MORE RETWEETS OR FAVORITES IF THEY HAVE A PICTURE?
 - QUESTION 10:  IMAGES OF THE GOLDEN RETRIEVERS (MY FAVORITE DOG BREED) BEST RATED AND WITH THE MOST NUMBER OF FAVORITES?
 
 Go find the answers! :)
 
## Author
Sara Vicente Calle - *Initial work* - [SaraVicente](https://github.com/SaraVicente)


## License 
This project is licensed under the MIT License - see the  [MIT License](https://github.com/SaraVicente/Udacity_Project4_Data_Wrangling/blob/master/LICENSE) for details
