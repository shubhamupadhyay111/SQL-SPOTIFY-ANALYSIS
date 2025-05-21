## 📊 Spotify Data Analysis — README

### 🗂️ Project Overview

This project involves creating and analyzing a database named `spotify`, which contains metadata and performance statistics of music tracks. The aim is to perform **Exploratory Data Analysis (EDA)** and answer key business or analytical questions using SQL queries.

---

### 🛠️ Database Setup

**Database Name:** `spotify`
**Main Table:** `spotify`

```sql
CREATE DATABASE spotify;

CREATE TABLE spotify (
    artist VARCHAR(255),
    track VARCHAR(255),
    album VARCHAR(255),
    album_type VARCHAR(50),
    danceability FLOAT,
    energy FLOAT,
    loudness FLOAT,
    speechiness FLOAT,
    acousticness FLOAT,
    instrumentalness FLOAT,
    liveness FLOAT,
    valence FLOAT,
    tempo FLOAT,
    duration_min FLOAT,
    title VARCHAR(255),
    channel VARCHAR(255),
    views FLOAT,
    likes BIGINT,
    comments BIGINT,
    licensed BOOLEAN,
    official_video BOOLEAN,
    stream BIGINT,
    energy_liveness FLOAT,
    most_played_on VARCHAR(50)
);
```

---

### 🔍 Exploratory Data Analysis (EDA)

The EDA section explores various aspects of the dataset, including:

* Total entries and distinct artists/albums
* Album types
* Duration statistics (max, min, average)
* Null/zero checks and cleanup
* Distribution of `channel` and `most_played_on` values

---

### 📈 Data Analysis Queries

Here are some key questions addressed using SQL:

1. **Tracks with over 1 billion streams**
2. **Album-artist mapping**
3. **Total comments for licensed tracks**
4. **Tracks that are singles**
5. **Number of tracks per artist**
6. **Average danceability per album**
7. **Top 5 high-energy tracks**
8. **Official video statistics (views & likes)**
9. **Total views per album**
10. **Tracks streamed more on Spotify than YouTube**
11. **Top 3 most-viewed tracks per artist (using window functions)**
12. **Tracks with above-average liveness**
13. **Energy range (max - min) per album**

---

### ✅ Data Cleanup

```sql
DELETE FROM spotify
WHERE duration_min = 0;
```

Zero-duration tracks were removed as part of data quality assurance.

---

### 📌 Notes

* Boolean values like `licensed` and `official_video` are checked using `'true'` as string literals (could be adjusted based on DBMS behavior).
* Some analytical queries use `COALESCE` to handle `NULL` values safely.
* CTEs (Common Table Expressions) and window functions are used for advanced analytics.

---

### 📅 Requirements

* PostgreSQL or any SQL engine that supports standard SQL (CTEs, window functions).
* SQL client or database interface for query execution.
