   #  My Favorite YouTube Program Data Analysis  :Project Overview
   ![credit card Image](https://github.com/germeengehad/Fav_YT_Program_Data/blob/master/youtube_1.jpeg)
   

-This project explores descriptive, predictive, and sentiment analysis for my favorite YouTube program. Inspired by my curiosity about why this program initially received fewer views and why I sometimes felt bored watching it, I decided to analyze its performance using data.

The program is published across three different YouTube channels, and I utilized the YouTube API to scrape data specifically from the relevant playlists. The analysis includes insights into viewer engagement, trends, and sentiment around the program.

I worked on this project using Jupyter Notebook, where I set up a virtual environment to install the necessary libraries. This repository reflects my passion for data analysis and my interest in understanding content performance on YouTube. 
  
# The Data Set
I obtained the dataset from three YouTube channels where my program was published. First, I set up a YouTube API client to fetch the required data. I created three datasets:

- channel_data: Contains details and statistics for the three channels.
- videos_data: Includes all video data from the targeted playlists.
- video_comments: Captures comments from all videos in the playlists.


# Web Scraping Details
- API Setup:
Prepared the API key using YouTube API documentation.
Retrieved the IDs of the three target channels.
Initialized the YouTube API client.
Specified the playlists associated with my program.

- Channel Statistics:
Created a function to fetch and compare statistics like:
subscriberCount
viewCount
videoCount

Video Details and Statistics:
Developed a function to retrieve video details and statistics, including:
Snippet: channelTitle, title, description, tags, publishedAt
Statistics: viewCount, likeCount, favoriteCount, commentCount, dislikeCount
Content Details: duration, definition, caption

- Video Comments:
Built a function to scrape comments for all videos.

- Data Storage:
Saved the collected video data into a CSV file for future analysis and reference.


# EDA for channels_data Dataset
- Data Preparation:
Converted the count columns (e.g., viewCount, subscriberCount, videoCount) to numeric format for accurate analysis.
Visualization:

Plotted the top-performing channels, incorporating Arabic text into the plot.
To handle Arabic writing correctly, created a specific dataset for visualization, adding a new column to adjust the text direction from right to left. While Arabic normally doesn’t require adjustments, this step ensured proper formatting in the plot.

- Insights:
Observed that AJ+ كبريت leads in views, subscribers, and video count.
Notably, this was the first channel where the targeted program was launched, suggesting that its established audience and reach might have significantly influenced the program's viewership and engagement.

- Further Analysis:
To validate this observation, performance trends of the program across AJ+ كبريت and the other channels could be analyzed to determine any notable differences in impact.

![Image](https://github.com/germeengehad/Fav_YT_Program_Data/blob/master/channels.png)

# Feature Engineering & EDA (for videos_data Dataset)

- Data Preprocessing
Type Conversion:
Converted the features ['viewCount', 'likeCount', 'favoriteCount', 'commentCount', 'dislikeCount'] to numerical data types.
Converted the publishedAt column to a datetime format for time-based analysis.
Data Cleaning:
Removed non-program videos like summaries or advertisements from the playlists. These were identified as videos shorter than 10 minutes, which were also considered outliers.

- Feature Engineering
Added New Features:
Number of Tags: A column to indicate the count of tags associated with each video.
Title Character Length: A column representing the number of characters in the video titles.

-  Analysis of Top Performing and Engagement Videos
Top Videos:
Highest Views: فلسطين .. حكاية الأرض | الدحيح | Palestine:
A captivating exploration of Palestine's history with exceptional storytelling and meticulous research. This episode has a significant viewership due to its engaging and educational content.
High Engagement: الدحيح | الملل:
A relatable dive into human psychology and boredom, blending humor and scientific insights. This episode has sparked meaningful conversations and resonates deeply with the audience.
![Image](https://github.com/germeengehad/Fav_YT_Program_Data/blob/master/max.png)

- Trend Analysis
View Count Trends:
Increased at the end of 2018, decreased in 2020, rose again in mid-2022, and declined by mid-2024.
Engagement Rate Trends:
Peaked in 2019 and declined by 2023.

- Key Questions and Findings
Does the number of likes and comments influence a video's view count?
Yes, likes and comments significantly impact view count.
Is there a relationship between the number of likes and comments?
Yes, there is a strong positive correlation.
What is the correlation between video duration and engagement rate?
A weak correlation exists.
Does the length of a video's title correlate with its view count?
Yes, there is a negative relationship; shorter titles tend to perform better.
Is there a correlation between the number of tags and the view count?
Weak correlation observed.

-  Channel and View Count Relationship
Used Spearman Correlation to analyze the relationship between channelTitle (categorical) and viewCount (numerical).
The Spearman correlation coefficient is -0.15, indicating a weak negative relationship.
While channel names can affect discoverability or audience trust, content quality, topic, and promotion are likely more critical determinants of view counts.

-  Most Frequently Used Words
Analyzed frequently viewed words in video titles and descriptions to identify key topics.
Created a word cloud to visualize these themes effectively, providing insights into the program’s focus areas.


# Comments Data Analysis for Future Video Topic Suggestions

- Data Cleaning:
Removed noise and applied text cleaning techniques to each comment in the dataset.
Displayed the cleaned comments for review.
Processed a total of 507 comments collected from the videos.

- Extracting Suggestions:
Defined a function to identify potential video topic suggestions based on commonly used phrases.
Created patterns to capture video suggestion phrases effectively.
Applied the function to extract actionable video suggestions directly from the comments.

