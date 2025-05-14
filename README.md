Instagram Data Analysis Project 📊

Project Description

This project analyzes Instagram post performance data to uncover insights about engagement patterns and content effectiveness. The analysis helps identify what types of posts perform best and when to post them.

Data Cleaning
First, we prepared the data by:

Selecting key columns: Media Type, Likes, Comments, and Created

Converting date strings to datetime format for time-based analysis

python
df = df[['Media Type', 'Likes', 'Comments', 'Created']]
df['Created'] = pd.to_datetime(df['Created'])
Key Analyses Performed
1. Performance Metrics
Calculated basic statistics (mean, min, max) for engagement metrics

Identified top-performing posts by likes and comments

2. Engagement Analysis
Created an engagement rate metric:

python
df['Engagement Rate'] = (df['Likes'] + df['Comments']) / df['Impressions'] * 100
Found posts with highest engagement relative to reach

3. Content Analysis
Compared performance across different media types

Analyzed hashtag effectiveness:

Counted hashtags per post

Examined relationship between hashtag count and engagement

4. Timing Analysis
Determined best posting times by:

python
df['Hour'] = df['Created'].dt.hour
df.groupby('Hour')['Likes'].mean()
5. Correlation Study
Created a heatmap to visualize relationships between metrics:

python
sns.heatmap(df[['Likes', 'Comments', 'Saves']].corr(), annot=True)
How to Run
Install requirements:

bash
pip install pandas matplotlib seaborn
Open and run the Jupyter notebook
