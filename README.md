📊 Social Media Analytics Database (SQL)

🔗 Repository:
SocialMedia_SQL GitHub Repository

📌 Project Summary

This project demonstrates the design and analysis of a Social Media Analytics Database using SQL.

The system stores user interactions such as posts, likes, comments, shares, followers, and trending content and generates meaningful insights through advanced SQL queries.

This project is ideal for showcasing SQL, database design, and data analysis skills.

🎯 Project Objectives

Design a relational database for social media platforms

Store user engagement and activity data

Perform analytics using SQL queries

Identify trending posts and active users

🗄️ Database Design

The project includes 15 normalized tables to simulate a real social media system:

Core Tables	Engagement Tables	Utility Tables

Users	Likes	Notifications

Posts	Comments	Messages

Followers	Shares	User_Logins

Hashtags	Saved_Posts	User_Settings

Post_Hashtags	Reports	Trending_Posts

🛠️ Technologies Used

SQL (MySQL / PostgreSQL compatible)

Relational Database Design

Joins & Aggregations

Data Analysis Queries

📈 Key Features

🔹 User Engagement Analytics

Count likes, comments, and shares per post

Find most active users

Analyze interaction patterns

🔹 Trending Post Detection

Posts are ranked based on engagement score using:

Likes

Comments

Shares

🔹 Follower Analysis

Most followed users

User growth insights

Engagement vs follower comparison

🔍 Important SQL Queries

Top 5 Most Liked Posts

SELECT p.post_id, p.content, COUNT(l.like_id) AS total_likes
FROM posts p
JOIN likes l ON p.post_id = l.post_id
GROUP BY p.post_id
ORDER BY total_likes DESC
LIMIT 5;

Most Active Users

SELECT u.user_id, u.username,
COUNT(DISTINCT p.post_id) AS posts,
COUNT(DISTINCT c.comment_id) AS comments,
COUNT(DISTINCT l.like_id) AS likes
FROM users u
LEFT JOIN posts p ON u.user_id = p.user_id
LEFT JOIN comments c ON u.user_id = c.user_id
LEFT JOIN likes l ON u.user_id = l.user_id
GROUP BY u.user_id
ORDER BY posts + comments + likes DESC;

Trending Posts by Engagement Score

SELECT p.post_id, p.content,
COUNT(DISTINCT l.like_id) +
COUNT(DISTINCT c.comment_id) * 2 +
COUNT(DISTINCT s.share_id) * 3 AS engagement_score
FROM posts p
LEFT JOIN likes l ON p.post_id = l.post_id
LEFT JOIN comments c ON p.post_id = c.post_id
LEFT JOIN shares s ON p.post_id = s.post_id
GROUP BY p.post_id
ORDER BY engagement_score DESC;

📂 Project Structure

SocialMedia_SQL/
│
├── database_schema.sql
├── sample_data.sql
├── analysis_queries.sql
└── README.md

🚀 How to Run the Project

1️⃣ Clone the repository

git clone https://github.com/Ganesh151205/SocialMedia_SQL.git

2️⃣ Import SQL files into MySQL/PostgreSQL

3️⃣ Run files in order:

database_schema.sql
sample_data.sql
analysis_queries.sql

4️⃣ Execute queries to view analytics results.

💡 Skills Demonstrated

SQL Joins (INNER, LEFT JOIN)

GROUP BY & Aggregation

Subqueries

Database Normalization

Data Analytics using SQL

👨‍💻 Author
Ganesh
