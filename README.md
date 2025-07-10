# Youtube_SQL_analysis
A data analyst’s take on YouTube — asking business-driven questions and answering them with SQL.

## 🎯 Objective

🔍💻 *How much insight can be uncovered with pure SQL?*  
Turns out — quite a lot.

This project presents a comprehensive **YouTube Analytics** case study using only **SQL** — not relying on complex window functions or advanced features, but instead emphasizing **business-focused questions** and **clean, efficient queries**.

Though beginner-friendly, the project maintains high standards in terms of **query clarity**, **data structure design**, and **strategic analysis**.

---

### ✨ Key Business Questions Explored

- What are the top YouTube channels by subscribers, and which content categories dominate?
- Which videos have surpassed the 100K views milestone?
- What is the total yearly revenue across channel categories?
- How does MrBeast’s video performance compare across key metrics?
- Which channels maintain a NOX score above 10 — and why is that significant?
- How do likes-to-comments and likes-to-views ratios vary across top-performing videos?
- Are there channels with below-average likes but above-average comments?

---

### 💡 Insight-Driven Approach

The focus of this project is not merely on writing SQL queries, but on framing **questions that reflect real-world strategic decision-making** in the content creation space — such as revenue attribution, audience engagement, and performance benchmarking.

✅ **Key Insight:** Advanced SQL is not a requirement for discovering high-value insights — understanding the **right questions** and using SQL purposefully delivers impactful outcomes.

---

## 🗃️ Database Schema

**Database Name**: `YOUTUBE`

### 1. `youtube_channels`
| Column         | Type             | Description               |
|----------------|------------------|---------------------------|
| channel_id     | INT (PK)         | Unique Channel ID         |
| channel_name   | VARCHAR(100)     | Name of the channel       |
| category       | VARCHAR(50)      | Content category          |
| subscribers    | VARCHAR(10)      | Subscriber count          |
| avg_views      | VARCHAR(20)      | Average views per video   |
| nox_score      | DECIMAL(10,2)    | NOX performance score     |

### 2. `channel_revenue`
| Column         | Type             | Description               |
|----------------|------------------|---------------------------|
| revenue_id     | INT (PK)         | Unique revenue ID         |
| channel_id     | INT (FK)         | Foreign key to channels   |
| monthly_revenue| DECIMAL(15,2)    | Revenue per month         |
| yearly_revenue | DECIMAL(15,2)    | Revenue per year          |

### 3. `channel_videos`
| Column         | Type             | Description               |
|----------------|------------------|---------------------------|
| video_id       | INT (PK)         | Unique video ID           |
| channel_id     | INT (FK)         | Foreign key to channels   |
| video_title    | VARCHAR(255)     | Title of the video        |
| upload_date    | DATE             | Upload date               |
| views          | BIGINT           | Number of views           |
| likes          | BIGINT           | Number of likes           |
| comments       | INT              | Number of comments        |

### 4. `channel_engagement`
| Column             | Type             | Description               |
|--------------------|------------------|---------------------------|
| engagement_id      | INT (PK)         | Unique engagement ID      |
| channel_id         | INT (FK)         | Foreign key to channels   |
| likes_per_video    | DECIMAL(10,2)    | Avg likes per video       |
| comments_per_video | DECIMAL(10,2)    | Avg comments per video    |
| shares_per_video   | DECIMAL(10,2)    | Avg shares per video      |

---

## 📊 SQL Questions

### 🟢 Easy
1. Find the `channel_name`, `category`, and number of `subscribers`.
<img width="1363" height="759" alt="image" src="https://github.com/user-attachments/assets/790d569b-5086-4992-b17e-2d504f06f85b" />

2. List all videos with `views > 100,000`.
<img width="1362" height="768" alt="image" src="https://github.com/user-attachments/assets/d4c3eec4-1f04-4d25-a6ce-75d23d6a49f7" />

3. Top 3 most liked videos.
<img width="1359" height="755" alt="image" src="https://github.com/user-attachments/assets/1840b9a2-eb61-4af2-809d-aeb4431255aa" />

4. Channels with `NOX score > 10`.
<img width="1361" height="766" alt="image" src="https://github.com/user-attachments/assets/6598162a-188c-4aea-b450-819d9c017138" />

5. Videos uploaded between `2024-03-01` and `2024-08-01`.
<img width="1365" height="823" alt="image" src="https://github.com/user-attachments/assets/21d53389-e58f-45ae-bee5-94b13dde1dc9" />

6. Count of channels per category.
<img width="1362" height="763" alt="image" src="https://github.com/user-attachments/assets/f143b4bc-0c20-4cdc-a205-38112d3080ee" />

7. Total yearly revenue of all channels.
<img width="1366" height="765" alt="image" src="https://github.com/user-attachments/assets/54fb0221-f525-414c-9c4b-1bf3d7191ab3" />

8. Videos uploaded by `'MrBeast'`.
<img width="1363" height="764" alt="image" src="https://github.com/user-attachments/assets/18181d33-7fff-495c-b39d-d6365306630d" />


### 🟠 Medium
9. Top 5 most subscribed YouTube channels.
<img width="1366" height="763" alt="image" src="https://github.com/user-attachments/assets/ab04b722-3e9d-4ea0-8cb8-14b3080c048e" />

10. Yearly revenue per channel category.
<img width="1366" height="770" alt="image" src="https://github.com/user-attachments/assets/f362a7be-f8fc-477e-9d39-287fc4113d45" />

11. Channels with `monthly revenue > $1,000,000` and `NOX < 10`.
<img width="1359" height="762" alt="image" src="https://github.com/user-attachments/assets/999f47e8-d4d0-49fe-99ec-3302de3a6077" />

12. Video with the highest likes-to-views ratio.
<img width="1360" height="766" alt="image" src="https://github.com/user-attachments/assets/acfd0a42-6071-458e-a33f-c25b42994b8d" />

13. Number of videos uploaded per channel in February 2024.
<img width="1362" height="764" alt="image" src="https://github.com/user-attachments/assets/16de9821-1112-4045-87f5-b52c34a3e6bb" />

### 🔴 Hard
14. Channels where `likes < avg likes` but `comments > avg comments`.
<img width="1364" height="759" alt="image" src="https://github.com/user-attachments/assets/1c23d973-7579-456f-bbaf-ce78bb1bea2b" />

15. Videos where `likes/comments ratio > avg ratio`.
<img width="1366" height="763" alt="image" src="https://github.com/user-attachments/assets/902de430-60d2-4f47-a866-56c34cd1033a" />

16. Channels where `views > avg views` but `NOX score < 5`.
<img width="1359" height="761" alt="image" src="https://github.com/user-attachments/assets/78a92fab-42e3-4cb7-a2c5-5d09cc28522f" />

---

## 🛠️ Tools Used

- SQL (MySQL )
- DB schema design
- Data analysis techniques (Aggregation, Filtering, Joins)
- Real-world scenario design

---
## 📌 Key Takeaway

Even with basic SQL, high-impact business insights can be derived when the right questions are asked — showcasing both analytical thought and structured execution.

## 🙌 Contributing

Feel free to fork the repo, open issues, or submit pull requests if you'd like to extend the analysis or add visualizations.

---

## 📢 Follow for More

If you found this helpful, don’t forget to ⭐ the repo and follow for more SQL-based data analysis projects!
