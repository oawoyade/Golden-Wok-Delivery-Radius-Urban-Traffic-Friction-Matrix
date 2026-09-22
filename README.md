# 🍜 Golden Wok — Delivery Radius & Urban Traffic Friction Analysis

## 📌 Project Overview

The **Golden Wok Delivery Radius & Urban Traffic Friction Dashboard** is a Power BI business intelligence project designed to analyse the commercial, operational, delivery, customer-experience and rider-performance dimensions of a food-delivery network.

The project transforms **5,000 delivery orders** into a four-page interactive Power BI dashboard covering:

- Order performance
- Profitability
- Delivery reliability
- Urban traffic friction
- Delivery radius
- Kitchen performance
- Customer satisfaction
- Rider performance
- Vehicle performance
- Meal-period demand

The objective is to help management understand how delivery distance, traffic conditions, weather, rider performance and customer experience influence business performance.

---

## 🎯 Business Objectives

The dashboard was developed to answer key business questions such as:

- How many orders are being processed?
- How much order value and profit are being generated?
- Which kitchens generate the highest order volume?
- Which delivery zones contribute the most demand?
- Are deliveries meeting promised delivery times?
- Does traffic congestion materially affect delivery performance?
- How does weather affect delivery time?
- Does profitability decline as delivery radius increases?
- Which kitchen and delivery-zone combinations are most profitable?
- Which vehicle types deliver faster?
- Which riders achieve stronger customer satisfaction?
- Which riders may require delivery-time coaching?
- Which meal periods generate the highest demand?

---

# 🧱 Data Model

The analytical solution uses a **star-schema data model** with `fact_orders` as the central transaction table.

## Fact Table

### `fact_orders`

Key fields include:

- Order ID
- Order Date
- Kitchen ID
- Rider ID
- Delivery Zone ID
- Time Slot ID
- Order Value
- Delivery Cost
- Order Profit
- Delivery Distance
- Actual Delivery Time
- Promised Delivery Time
- Traffic Friction Score
- Customer Rating
- Food Temperature on Arrival
- Distance Band
- Customer Rating Band

## Dimension Tables

### `dim_kitchen`

Contains:

- Kitchen ID
- Kitchen Name
- Location
- LGA
- Latitude
- Longitude
- Kitchen Capacity
- Date Opened
- Active Status

### `dim_rider`

Contains:

- Rider ID
- Rider Name
- Assigned Kitchen
- Vehicle Type
- Average Rider Rating
- Average Speed
- Experience
- Active Status

### `dim_delivery_zone`

Contains:

- Zone ID
- Zone Name
- Zone LGA
- Zone Tier
- Baseline Delivery Time
- Average Zone Traffic Index
- Population Density
- Restricted Zone Flag

### `dim_time_slot`

Contains:

- Day of Week
- Hour Number
- Hour of Day
- Meal Period
- Rush-Hour Flag
- Rush-Hour Category
- Weekend Flag

### `Date`

A dedicated Date table was created for time-intelligence analysis.

Key fields include:

- Date
- Day
- Day Name
- Month
- Month Number
- Month Year
- Quarter
- Year

A dedicated DAX Measures table was also used to organise the analytical calculations.

---

# 📊 Dashboard Pages

## 1️⃣ Executive Performance Overview

This page provides a high-level view of Golden Wok's commercial performance.

### Key KPIs

| KPI | Result |
|---|---:|
| Total Orders | **5,000** |
| Total Order Value | **₦380.56M** |
| Total Profit | **₦2.49M** |
| Average Order Value | **₦76.11K** |
| Profit Margin | **0.65%** |

### Key Visuals

- Monthly Order Volume Trend
- Orders by Kitchen
- Orders by Delivery Zone Tier
- Monthly Order Value vs Total Profit
- Golden Wok Order-to-Delight Journey

### Key Insight

Order volume is distributed relatively evenly across the four kitchens, while Tier 2 and Tier 3 delivery zones account for a significant proportion of total demand.

Despite generating approximately **₦380.56M in order value**, overall profit margin remains relatively thin at approximately **0.65%**.

---

## 2️⃣ Urban Traffic & Delivery Reliability

This page evaluates delivery performance under different traffic, weather and operating conditions.

### Key KPIs

| KPI | Result |
|---|---:|
| Avg Delivery Time | **500.05 mins** |
| Avg Promised Time | **505.02 mins** |
| On-Time Delivery % | **50.06%** |
| Late Order Rate | **49.94%** |
| Avg Traffic Friction | **5.45 / 10** |

### Key Visuals

- Actual vs Promised Delivery Time
- Delivery Time by Traffic Band
- Delivery Time by Weather Condition
- Traffic Friction vs Delivery Time
- Delivery Time by Zone
- Rush Hour vs Off-Peak Delivery Performance

### Key Insight

Only around **50% of deliveries meet their promised delivery time**.

Heavy Rain records the longest average delivery time, while Sunny conditions show the lowest.

Traffic friction does not show a strong linear relationship with delivery duration, suggesting that congestion alone does not explain delivery delays.

---

## 3️⃣ Delivery Radius & Profitability Intelligence

This page explores the relationship between delivery distance, cost and profitability.

### Key KPIs

| KPI | Result |
|---|---:|
| Avg Delivery Distance | **17.55 km** |
| Total Delivery Cost | **₦30.50M** |
| Avg Delivery Cost | **₦6.10K** |
| Avg Profit per Order | **₦497.70** |
| Total Profit | **₦2.49M** |

### Key Visuals

- Orders by Distance Band
- Average Delivery Cost by Distance Band
- Total Profit by Delivery Zone
- Total Profit vs Average Profit per Order
- Kitchen Profitability Pulse

### Distance Distribution

| Distance Band | Orders |
|---|---:|
| 0–5 km | 704 |
| 5–10 km | 713 |
| 10–15 km | 707 |
| 15–20 km | 751 |
| 20–30 km | **1,443** |
| 30+ km | 682 |

The **20–30 km band** generates the largest order volume.

### Key Insight

Longer delivery distances do not automatically produce lower profitability within the supplied dataset.

Profitability varies more meaningfully by **Kitchen × Delivery Zone** combination than by distance alone.

---

## 4️⃣ Customer Experience, Rider Performance & Market Demographics

This page evaluates customer satisfaction, rider performance, vehicle performance and demand patterns.

### Key KPIs

| KPI | Result |
|---|---:|
| Avg Customer Rating | **3.00 / 5** |
| Low Rating % | **37.50%** |
| Active Riders | **60** |
| Avg Delivery Time | **500.05 mins** |
| On-Time Delivery % | **50.06%** |

### Key Visuals

- Customer Rating Distribution
- Average Delivery Time by Vehicle Type
- Low Rating % by Vehicle Type
- Orders by Meal Period
- Rider Performance Arena

### Vehicle Performance

Approximate average delivery times:

| Vehicle Type | Avg Delivery Time |
|---|---:|
| Motorcycle (Okada) | **490 mins** |
| Tricycle (Keke) | **493 mins** |
| Electric Motorcycle | **497 mins** |
| Bicycle | **506 mins** |
| Cargo Motorcycle | **508 mins** |

### Meal-Period Demand

| Meal Period | Orders |
|---|---:|
| Afternoon | **1,137** |
| Dinner | 800 |
| Mid-Morning | 706 |
| Early Morning | 615 |
| Breakfast | 501 |
| Lunch | 460 |
| Early Dinner | 451 |
| Late Night | 330 |

### Key Insight

Customer satisfaction averages approximately **3.0/5**, while **37.5% of orders receive ratings below 2.5**.

The fastest vehicle type does not necessarily achieve the strongest customer satisfaction, indicating that rating performance is influenced by more than delivery speed alone.

---

# 🎨 Custom HTML/CSS Visuals

A key feature of this project is the use of DAX-driven HTML/CSS visuals to create more distinctive executive-style analytics.

## Golden Wok Order-to-Delight Journey

Tracks how orders progress through service-quality milestones:

- Orders Placed
- Delivered On-Time
- Arrived Hot
- Rated 4★ or Higher
- Golden Standard 4.5★+

---

## Kitchen Profitability Pulse

This custom visual compares each kitchen's average profit per order across:

- Core Zone
- Adjacent Zone
- Extended Zone
- Outer Zone

Colour and bar length are used to indicate profitability strength.

---

## Rider Performance Arena

This custom visual separates eligible riders into:

### ⭐ Top Rated Riders

Riders with the strongest customer ratings.

### ⏱ Coaching Watchlist

Riders with the longest average delivery times.

Only riders with **50+ orders** are eligible, reducing low-volume noise.

---
