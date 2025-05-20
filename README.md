# 📊 YouTube Analytics Dashboard using Power BI & YouTube API

This project demonstrates how to extract data from the YouTube Data API, clean and preprocess it, and then build an interactive analytics dashboard using Power BI. The goal is to provide actionable insights into video and channel performance across a YouTube account.

---

## 🔍 Project Highlights

- ✅ Extracted real-time data using the **YouTube Data API**
- ✅ Cleaned and transformed raw data (ISO 8601 durations, nested tags, etc.)
- ✅ Built a visually engaging and interactive **Power BI dashboard**
- ✅ Performed detailed video-level and channel-level analysis
- ✅ Included metrics such as views, likes, comments, video length, and upload time

---

## 🧾 Data Columns Extracted

From the YouTube Data API, the following data was collected and analyzed:

- `channel_id` – Unique ID of the channel
- `video_id` – Unique ID for each video
- `channelTitle` – Name of the channel
- `title` – Video title
- `description` – Description of the video
- `tags` – List of associated tags
- `publishedAt` – Date and time of video publication
- `viewCount` – Total number of views
- `likeCount` – Total number of likes
- `favoriteCount` – Number of times favorited
- `commentCount` – Number of comments
- `duration` – Length of the video (ISO 8601 format, converted to minutes)
- `definition` – Video quality (HD or SD)
- `caption` – Whether the video has closed captions

---

## 📊 Dashboard Features

- **Channel Overview**
  - Total videos, views, likes, and comments
  - Top 5 performing channels
- **Video Engagement**
  - Top 10 videos by views, likes, and comments
  - Scatter plots for likes vs. views
  - Engagement rate: `(likes + comments) / views`
- **Publishing Trends**
  - Views over time by date
  - Heatmap of best day and time to post
- **Video Properties**
  - Distribution of video duration
  - Breakdown of caption availability and video definition (HD/SD)
- **Tags Analysis**
  - Most frequent tags
  - Tags with highest average views

---

## 🧮 Key DAX Measures

```DAX
Total Views = SUM(Videos[viewCount])
Total Likes = SUM(Videos[likeCount])
Total Comments = SUM(Videos[commentCount])
Engagement Rate = DIVIDE(SUM(Videos[likeCount]) + SUM(Videos[commentCount]), SUM(Videos[viewCount]), 0)
Views Per Day = DIVIDE(SUM(Videos[viewCount]), DATEDIFF(MIN(Videos[publishedAt]), TODAY(), DAY), 0)

---

##  Tools & Technologies Used

YouTube Data API – For data extraction
Power Query – For data cleaning and transformation
Power BI Desktop – For visualization and dashboard creation
DAX – For calculated metrics and aggregations

---
