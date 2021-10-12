## Date created
12th June 2021


## Project Title
Data Wrangling


## Description
This project gathers data from a variety of sources and in a variety of format using Python and its libraries. It then assess the data for its quality and tidiness, then cleans it for analysis. Thereafter, the data is analysed to gain valuable insight and present it through data visualisation.


## Files used
* twitter-archive-enhanced.csv
* image_predictions.tsv
* twitter-api.py
* tweet-json.txt
* twitter_archive_master.csv (combined dataset)
* wrangle_act.ipynb


## Dataset
The dataset consists of over 2300 records from WeRateDogs Twitter archive. WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog. These ratings almost always have a denominator of 10. However the numerators are almost always greater than 10 (11/10, 12/10, 13/10, etc.) hence data cleaning is necessary. On top of this, additional data on retweet count and favorite count was gathered from Twitter's API which then combined with the first dataset, and analysed.

1. WeRateDog Twitter archive (twitter_archive_enhanced.csv)
This data was readily available in CSV file. To read CSV file using Python, import Pandas library and use read_csv function. In this project, this dataset is named as twitter_archive.

2. Tweet image predictions (image_predictions.tsv)
This data was downloaded from a website using Requests library, and then stored as a .tsv file. It was then read using Pandas library and named as image_pred.

3. Retweet and favorite count from Twitter API (tweet_json.txt)
This JSON data was queried from Twitter API using Python’s Tweepy library. Each tweet’s JSON data was written to its own line into a tweet_json.txt file and was read line by line into a Pandas DataFrame. This data is named as rt_fave.


## Summary of Findings
p1, p2, and p3 are confidence score of the image prediction outcomes. Through analysis of confidence mean of this data, it was found that:
1. The image prediction outcomes with the highest confidence mean for p1, p2, and p3 are ping-pong ball, porcupine, and french horn respectively.
2. The most often predicted dog breed are Golden Retriever for p1 and Labrador Retriever for both p2 and p3.
3. The most favorite dog breed for are Golden Retriever for p1 and Labrador Retriever for both p2 and p3.


## Key Insights for Presentation
In the cleaning process, I addressed some of the Tidiness issue first, such as merging dog stages column and merging all tables into one.

These are the steps that were taken when cleaning the dog stages columns:
1. Handle 'None' in the 4 dog stages columns
2. Merge the 4 columns into one column
3. Handle rows that are having multiple stages
4. Handle missing values
5. Drop the original 4 dog stages columns

All the tables are merged into one using left outer join because we want the merged table to have all of the tweet_archive records even when there is not matching record found in the image_pred and rt_fave table.

In the final step, I reviewed all the data and considered which ones that may not be useful in the data analysis, as follow:
- in_reply_to_status_id
- in_reply_to_user_id
- retweeted_status_id
- retweeted_status_user_id
- retweeted_status_timestamp
- rating_numerator
- rating_denominator
- name

I dropped those columns and saved the dataset into a .csv file, twitter_archive_master.csv.


## List of Resources
- udacity.com
- twitter.com


## Credits
* [Udacity](udacity.com)
