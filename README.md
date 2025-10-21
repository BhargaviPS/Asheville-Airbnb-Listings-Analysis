# 🏡 Asheville Airbnb Listings Analysis

## 📘 Introduction
This project explores Airbnb listings in Asheville to understand host behavior, pricing trends, property availability, and user review patterns. The analysis combines listing-level details with review history to uncover insights into the Airbnb market dynamics in Asheville.

---

## 🎯 Objectives
The key objectives of this analysis are:

- To explore the overall distribution and characteristics of Airbnb listings in Asheville.
- To examine pricing trends by comparing price by `neighbourhoods` and `minimum_nights` and so on.
- To understand review and demand patterns.
- To derive insights from the hosts
- To give recommendations that can inform hosts, customers, or marketers.

---

## 🗂️ Dataset and Context
Two datasets were used:

1. **Listings Dataset** contains detailed information about each property such as:
   - `id`, `name`, `host_id`, `host_name`, `neighbourhood`, `room_type`, `price`, `minimum_nights`, `availability_365`, `number_of_reviews`, `reviews_per_month`, `last_review`, and others.  
   - Each row represents a **unique listing (property)**.

2. **Reviews Dataset** contains:
   - `listing_id`, `date`  
   - Each row represents a **review** for a particular listing on a specific date.

**Relationship:**  
One listing can have multiple reviews (1-to-many relationship).  
After merging, listings without reviews were excluded from trend analysis since they provide no review-related information.

---

Credit to **[Analyst Builder](https://www.analystbuilder.com/projects/asheville-airbnb-listings-analysis-hQNaU)** for the datasets and the directions for the analysis.

---

## 🧰 Libraries Used
The analysis was performed in **Python**, mainly using:

- `pandas` – for data wrangling and analysis  
- `numpy` – for numerical computation  
- `matplotlib` and `seaborn` – for visualization  

The jupyter notebook is attacched for reproducibility.

---

## 🧹 Data Cleaning
The following data preparation steps were undertaken:

- **Dropped irrelevant columns** and renamed datasets for clarity.  
- **Filtered out old listings** with last reviews before 2021. 
- **Dropped possible duplicates** and none was found.
- **Merged** the listings and reviews datasets on `listing_id`.  
- **Handled missing values** by imputing the `price` column with the **median**, especially due to the skewed distributions from outliers.
- **Identified and handled outliers** using percentile-based capping (Winsorization) for variables like `price` and `minimum nights`.  
- **Converted dates** to datetime format for proper filtering and trend analysis.  
- **Filtered** reviews between 2021 and 2025 to focus on current trends.

---

## 📊 Key Findings
- The **price distribution** is highly right-skewed (skew = 3.3, kurtosis = 14), indicating a few extremely high-priced listings which may result from luxurious/premium listings. Average price was $169 with a median $128.00

- **Entire home/apartment** is the commonest room type having a percentage share of 89%. Private room has close to 10% share of the room types.

<p align="center">
  <img src="images/Distribution of room_types.png" width="600"/>
</p>

- The distribution of the **`calculated_host_listings_count`** shows that most of the hosts have less than 3 listings (median = 2) with a few hosts having more than 10 listings. One host has more than 100 listings!

- The distribution of the **`availability_365`** shows a slightly negatively-skewed distribution. The median availabilty is 254 days and an average of 224 days. This means that most listings are available for booking for most part of the year. At the extreme left, it shows a good number of listings have a small `availability_365` < 5.

- **Neighbourhood `28806`** has the cheapest average price amongst the neighbourhoods. It is also very likely that since neighbourhood `28806` is highly competitive (with 800 listings),  hosts may be compelled to reduce prices to stay competitive.

- **Neighbourhoods `28806`, `28801`, `28804`, `28803` and `28805`** are the top-5 neighbourhoods that generate most guest activity.

- **Market demand** begun to rise steadily from 2011 to 2019 and dipped slightly in 2020 probably due to the impact of COVID 19. From 2020, demand has grown every year but saw its all time high in 2023 before dipping in 2024.

<p align="center">
  <img src="images/Historic trend.png" width="45%" style="margin-right:10px"/>
  <img src="images/Recent years trend.png" width="45%"/>
</p>

<br>

- **Review activities/demand peaks in July** and decline in November, December and January (the winter period).

<p align="center">
  <img src="images/Monthly_trend.png" width="600"/>
</p>

<br>

- **Sunday** leads as the day with most review activites with **67274 reviews representing  a little over one-third (33.8%)** of all reviews. It is possible most people are relaxed on Sundays and so get time for activities like writing reviews. It could also mean most checkouts happen over the weekends.


<p align="center">
  <img src="images/Day_comparison.png" width="600"/>
</p>

---

## 💬 Conclusion and Insights
- The Asheville Airbnb market looks promising for busineses with the right straetgies: a few high-value properties dominate earnings while most operate at moderate prices.

- Review activity is consistent with seasonal tourism trends. Weekends and Sundays show spikes and dips during the winter.

- Property type with strong opportunities are **`Entire home/Apt`** which has a market share of over 89%. **Neighbourhoods `28806`, `28801` and `28803`** should be considered by businesses and individuals since they are the market hotspots in Asheville.

- The demand is active on all days of the month. Sunday is the most active review day taking over 1/3 of the reviews. It also suggests that most checkouts occur during the weekends and that bookings may be high from Wednesdays towards Saturdays. Marketing campaigns can be intensified from midweek towards the weekend.


---

## 🔍 Opportunity for Further Analysis
Future analysis could explore:

- **Price prediction modeling** using features like room type, location, and host characteristics.  
- **Host-level performance** (e.g., identifying superhosts, host response rates, or occupancy estimation).  
- **Sentiment analysis** on review text (if available).  
- **Geospatial analysis** — mapping listings by neighborhood to study location-based price dynamics.  

---


📬 Contact
If you'd like to connect, collaborate, or discuss this project further:

📧 Email: mathiasofosu2@gmail.com

💼 LinkedIn: [Mathias Ofosu](https://linkedin.com/in/mathias-ofosu)

🧠 GitHub Profile: [Mathias Ofosu](https://github.com/MKOfosu)

 Twitter/X: [Mathias Ofosu](https://x.com/MKOfosu)

Feel free to reach out. I’m always open to data-driven conversations.