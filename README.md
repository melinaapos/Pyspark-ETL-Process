# About the project
This project is an implementation of an **ETL** (Extract Transform Load) process with **Pyspark** (the Python API for Apache Spark).
This includes reading from two different files, tranforming the data to make it more useful for the needs of this project and writing the output to a parquet file. The purpose is to find out which youtube categories are more popular based on how many views they have.

Some of the topics that are covered in this project are:


**Extract**
- Extract data by reading the files (csv, json) into Dataframes

**Transform**
- Data cleaning
- Selecting only certain columns
- Join data from two different sources
- Aggregations

**Load**
- Write the output dataset to a parquet file

## Environment
The selected environment for this project is Google Colab which is a hosted Jupyter Notebook service that requires no setup to use and provides free access to computing resources. 


## Data Description
The dataset that was used was the *Trending Youtube Video Statistics* dataset which includes data on daily trending Youtube videos from several months of 2020 to 2022. The dataset can be found in the following link: https://www.kaggle.com/datasets/datasnaek/youtube-new. For this project was used data from Britain. This includes two files.

The *BR_youtube_trending_data.csv* file provides information about the videos on Youtube and contains the following fields:
+ video_id
+ title
+ publishedAt
+ channelId
+ channelTitle
+ categoryId
+ trending_date
+ tags
+ view_count
+ likes
+ dislikes
+ comment_count
+ thumbnail_link
+ comments_disabled
+ ratings_disabled
+ description

The *BR_category_id.json* file provides information about the categories that the videos are labeled with and contains the following fields:
+ kind
+ etag
+ items
  + kind
  + etag
  + id
  + snippet
    + title
    + assignable
    + channelId


The two files share a common column the *categoryId* from the *BR_youtube_trending_data.csv* and the *id* from the *BR_category_id.json*. In the *BR_category_id.json* dataset The *id* column is matched to the *title* column which describes a category of Youtube videos (Music, Sports,  etc.). Thus, the category in which each video is assigned can be determined from the two files.