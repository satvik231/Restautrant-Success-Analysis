# Yelp Restaurant Success: User Engagement Analysis

Does user engagement (reviews, tips, check-ins) predict restaurant success? This project analyzes a subset of the Yelp dataset covering **8 metropolitan areas across the USA and Canada** to find out.

**Tech stack:** `[SQL / Python / Pandas / Matplotlib / Seaborn / Jupyter]` 

---

## 1. Problem Statement
In a competitive market like the restaurant industry, understanding the factors that influence business success is crucial for stakeholders. This project investigates the relationship between user engagement (reviews, tips, check-ins) and business success metrics (review count, ratings) for restaurants.

## 2. Research Objectives
1. Quantify the correlation between user engagement and review count / average star rating
2. Analyze the impact of sentiment on review count and average star rating
3. Identify time trends in user engagement

## 3. Hypotheses
- Higher user engagement correlates with higher review counts and ratings
- Positive sentiment in reviews and tips contributes to higher ratings and review counts
- Consistent engagement over time is associated with sustained business success

## 4. Data Overview
- Yelp subset shared as **5 JSON files**: `business`, `review`, `user`, `tip`, `checkin`
- JSON files loaded into a database for easy retrieval
- Of ~**150K** businesses, ~**35K** are open restaurants

## 5. Analysis & Findings

### 5.1 Distribution of success metrics

| Metric | Review Count | Star Rating |
|---|---|---|
| Average | 55.98 | 3.48 |
| Min | 5 | 1.0 |
| Max | 248 | 5.0 |
| Median | 15 | 3.5 |

### 5.2 Highest rating vs. highest review count
<img width="700" alt="01_top_review_count" src="https://github.com/satvik231/Restautrant-Success-Analysis/blob/main/01_top_review_count.png" />

- Top-rated (5.0) restaurants are small independents with 7 to 77 reviews (e.g., Two Birds Cafe, La Bamba)
- The most-reviewed are large chains (McDonald's 16,490 reviews, avg 1.87★)
- **Higher ratings do not guarantee higher review counts, or vice versa.** Success is not determined by ratings or review counts alone.

### 5.3 Do restaurants with higher engagement have higher ratings?
<img width="800" alt="02_engagement_by_rating" src="https://github.com/satvik231/Restautrant-Success-Analysis/blob/main/02_engagement_by_rating.png" />

- Average reviews, check-ins, and tips increase as ratings improve from 1 to 4 stars
- Engagement peaks at **4 stars** and drops at 5.0, suggesting either a saturation point or a small, selective audience

### 5.4 Correlation between reviews, tips, and check-ins
<img width="450" alt="03_engagement_correlation" src="https://github.com/satvik231/Restautrant-Success-Analysis/blob/main/03_engagement_correlation.png" />

Correlations of 0.70 to 0.75 show engagement across platforms is interlinked: higher activity in one tends to go with higher activity in others.

### 5.5 High-rated vs. low-rated businesses
<img width="600" alt="04_high_vs_low_rated" src="https://github.com/satvik231/Restautrant-Success-Analysis/blob/main/04_high_vs_low_rated.png" />

| Category | Reviews | Check-ins | Tips |
|---|---|---|---|
| High-Rated | 63.10 | 80.72 | 8.07 |
| Low-Rated | 37.15 | 64.84 | 5.46 |

### 5.6 Success metrics by state and city
**Philadelphia** has the highest success score (high ratings combined with active engagement), followed by **Tampa, Indianapolis, and Tucson**.

<img width="500" alt="city_map" src="https://github.com/satvik231/Restautrant-Success-Analysis/blob/main/city_map.jpeg" />

### 5.7 Engagement patterns over time
- High-rated (3.5+) restaurants show steady or growing engagement over time
- A sharp **COVID-19 drop** appears in tip and review engagement in 2020
- **Trend & seasonality:** review counts trend upward, tip counts trend downward, and the year start/end (**Nov to Mar**) is the most engaging period

<img width="500" alt="trends" src="https://github.com/satvik231/Restautrant-Success-Analysis/blob/main/trends.jpeg" />

### 5.8 Sentiment (useful, funny, cool) vs. success
<img width="500" alt="05_sentiment_correlation" src="https://github.com/satvik231/Restautrant-Success-Analysis/blob/main/05_sentiment_correlation.png" />

Useful, funny, and cool counts correlate positively with success score (0.64, 0.45, and 0.66), with `review_count` at 0.70.

### 5.9 Elite vs. non-elite users
<img width="650" alt="06_elite_users" src="https://github.com/satvik231/Restautrant-Success-Analysis/blob/main/06_elite_users.png" />

Elite users are only **4.59%** of users but write **44.05%** of all reviews.

### 5.10 Busiest hours
Engagement peaks from **4 PM to 1 AM**, suggesting higher dining-out demand in the evening and night.

<img width="500" alt="busiest_hour" src="https://github.com/satvik231/Restautrant-Success-Analysis/blob/main/busiest_hour.jpeg" />

## 6. Recommendations
- Partner with elite users to amplify promotions, brand awareness, and customer acquisition
- Adjust operating hours and staffing, or run promotions, to capitalize on peak hours
- Low-rated restaurants should improve service quality and respond to customer feedback
- Cities with high success scores are opportunities for chains to expand or invest further

## 7. Repository Structure
```
├── data/        # raw and cleaned datasets
├── notebooks/   # analysis notebooks
├── sql/         # queries
├── images/      # charts used in this report
└── README.md
```
