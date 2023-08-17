# YouTube-Trending-Videos-Data-Analysis
The dataset includes data gathered from videos on YouTube that are contained within the trending category each day.
Link to the code: https://github.com/SushreeSangitaPanda/SushreeSangitaPanda/blob/1bc5892d2289a63010ab5b7779816bcb00a6f448/bmg_task.ipynb

This repository contains a comprehensive data analysis of trending videos on YouTube using Python libraries such as pandas, seaborn, SentimentIntensityAnalyzer from NLTK, and more. The analysis aims to provide insights into the characteristics and trends of YouTube videos that have gained popularity. The dataset used for this analysis includes the following columns: video_id, title, publishedAt, channelId, channelTitle, categoryId, trending_date, tags, view_count, likes, dislikes, comment_count, thumbnail_link, comments_disabled, ratings_disabled, and description.

## How to Use the Repository

1. **Data Files:** The dataset is present in two different CSV files:

   a. `YoutubeDataCleaned.csv`: Contains the primary data for analysis, including video information like video_id, title, publishedAt, channelId, channelTitle, categoryId, trending_date, tags, view_count, likes, dislikes, comment_count, thumbnail_link, comments_disabled, ratings_disabled, and description. Load the data using:
   
   ```python
   import pandas as pd
   
   df = pd.read_csv('path_to_file/YoutubeDataCleaned.csv', encoding='latin-1')
   ```
   
   b. `Category Names.csv`: Contains the mapping of category IDs to category names. This file is necessary for adding meaningful category names to the dataset. Load the data using:
   
   ```python
   df_category = pd.read_csv('path_to_file/Category Names.csv')
   ```

2. **Merging Data:** To create a unified dataset with category names, you can merge the two dataframes using the `category_id` as the key. Here's how to do it:
   
   ```python
   df_dummy = pd.merge(df, df_category, how='outer', left_on='category_id', right_on='id')
   ```

3. **Analysis Code:** The code used for performing the analysis can be found in the "analysis" directory. It's organized into Jupyter Notebook files and Python scripts. You can follow the steps in these files to replicate the analysis on your own machine.

4. **Results and Visualizations:** The "results" directory contains visualizations, graphs, and summary statistics generated during the analysis.




## Key Results of the Analysis

1. **Dataset Information:** The dataset was collected over two years, with 61% of the data from 2018 and 39% from 2017. It encompasses information about trending videos across a span of 125 days.

2. **Average Views:** The average number of views for a trending video is approximately 1,329,987, indicating a significant level of engagement.

3. **Likes Distribution:** The majority of trending videos have 40,000 likes or less, indicating a wide range of audience engagement levels.

4. **Top Channel:** The channel "ESPN" stands out as the producer of the most trending videos within the dataset.

5. **Common Title Keywords:** Through analysis, it was observed that words like "official", "video", "trailer", "music", "show", "new", "live", "first", "time", and "HD" frequently appear in trending video titles.

6. **Tag Utilization:** Almost all trending videos use tags, with an average of 13 tags per video.

7. **Impact of Comments Disabled:** Videos with disabled comments tend to have fewer views compared to those with open comment sections.

8. **Ratings and Comments:** Among the trending videos, 139 out of 22,385 prevented users from rating them. Only 80 videos had both comments and ratings disabled.

9. **Geographical Insights:** The state of WA (Washington) contributed the highest number of views, with the city of Pensacola leading in terms of view count.



## Conclusion

This YouTube Trending Videos Data Analysis provides valuable insights into the characteristics of videos that achieve trending status on the platform. The analysis highlights trends in viewer engagement, popular keywords in titles, channel performance, and the impact of user interaction features like comments and ratings. The provided code and results enable you to delve deeper into the dataset and draw your own conclusions about the factors contributing to a video's popularity on YouTube.

