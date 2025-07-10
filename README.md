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

3. Top 3 most liked videos.

4. Channels with `NOX score > 10`.

5. Videos uploaded between `2024-03-01` and `2024-08-01`.

6. Count of channels per category.

### 🟡 Medium
7. Total yearly revenue of all channels.
8. Videos uploaded by `'MrBeast'`.
9. Top 5 most subscribed YouTube channels.
10. Yearly revenue per channel category.
11. Channels with `monthly revenue > $1,000,000` and `NOX < 10`.
12. Video with the highest likes-to-views ratio.
13. Number of videos uploaded per channel in February 2024.

### 🔴 Hard
14. Channels where `likes < avg likes` but `comments > avg comments`.
15. Videos where `likes/comments ratio > avg ratio`.
16. Channels where `views > avg views` but `NOX score < 5`.

---

## 🛠️ Tools Used

- SQL (MySQL )
- DB schema design
- Data analysis techniques (Aggregation, Filtering, Joins)

---

## 🙌 Contributing

Feel free to fork the repo, open issues, or submit pull requests if you'd like to extend the analysis or add visualizations.

---

## 📢 Follow for More

If you found this helpful, don’t forget to ⭐ the repo and follow for more SQL-based data analysis projects!
