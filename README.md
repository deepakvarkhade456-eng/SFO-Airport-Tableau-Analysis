# SFO-Airport-Tableau-Analysis
# San Francisco SFO Airport Analysis — Tableau Project Documentation

> **Project type:** Tableau Data Analysis & Dashboard  
> **Domain:** Aviation / Airport Operations  
> **Dataset:** `AIRPORT ANALYSIS(3).xlsx`  
> **Airport:** San Francisco International Airport (SFO)  
> **Analysis period:** March 1–31, 2020  
> **Primary focus:** Flight activity, route performance, route distance, and airport traffic trend

---

# Slide 1 — Project Title

## San Francisco SFO Airport Analysis

### Tableau Dashboard Documentation

This project analyzes flight-event information associated with San Francisco International Airport (SFO).

The dashboard is designed to provide a simple view of:

- Total flight activity
- Number of unique routes
- Most frequent routes
- Long-distance routes
- Daily airport traffic
- Route connectivity around SFO
- Airline and flight-event information available in the dataset

---

# Slide 2 — Project Overview

## What is the project about?

The **SFO Airport Analysis** project studies historical airport flight data to understand how flight activity is distributed across dates, routes, airlines, and airport connections.

The Tableau dashboard converts the raw flight-event dataset into visual KPIs, charts, and a route map.

### Main questions addressed

1. How many flight events are recorded?
2. How many different routes are connected with SFO?
3. Which routes have the highest number of flights?
4. Which routes cover the longest distances?
5. How does daily flight traffic change during March 2020?
6. How are routes distributed geographically?
7. Which airlines contribute the most flight events?

---

# Slide 3 — Business Objective

## Objective

The objective of this project is to analyze SFO airport flight activity and present the information in an easy-to-understand Tableau dashboard.

### Business purpose

The analysis can help airport and aviation stakeholders understand:

- Overall flight activity
- Route demand and connectivity
- High-volume routes
- Long-distance route coverage
- Changes in daily traffic
- Airline participation
- Arrival/departure event distribution

### Expected value

The dashboard can support:

- Airport traffic monitoring
- Route planning
- Operational analysis
- Airline performance review
- Historical trend analysis
- Business reporting and presentation

---

# Slide 4 — Dataset Overview

## Dataset structure

The workbook contains two sheets:

| Sheet | Purpose |
|---|---|
| `Sheet1` | Daily flight totals used for the traffic trend |
| `Air travel data` | Detailed flight-event records used for the main analysis |

### Main dataset size

- **Rows:** 88,532
- **Columns:** 18
- **Date range:** 01 March 2020 to 31 March 2020
- **Total flight events:** 88,532
- **Unique routes:** 271
- **Unique dates:** 31

The detailed `Air travel data` sheet is the primary source for the Tableau dashboard.

---

# Slide 5 — Data Dictionary

## Important dataset columns

| Column | Meaning / Use |
|---|---|
| Geometry Coordinates 0 0 | Longitude of the first route point |
| Geometry Coordinates 0 1 | Latitude of the first route point |
| Geometry Coordinates 1 0 | Longitude of the second route point |
| Geometry Coordinates 1 1 | Latitude of the second route point |
| Geometry Type | Geometry format used for the route |
| Properties Edtf Cessation | Cessation/end-date related field |
| Properties Edtf Inception | Start/inception-date related field |
| Properties Flysfo Actual Timestamp | Actual flight-event timestamp |
| Properties Flysfo Airline | Airline associated with the flight event |
| Properties Flysfo Base Airline | Base/operating airline information where available |
| Properties Flysfo Base Flight Number | Base flight number where available |
| Date | Flight-event date |
| Properties Flysfo Estimated Timestamp | Estimated flight-event timestamp |
| Properties Flysfo Event | Flight event category/code |
| Properties Flysfo Flight Number | Flight number |
| Properties Flysfo Gate | SFO gate information where available |
| Route | Origin–destination route, such as `SFO-LAX` |
| No. of flight | Flight-event count used for aggregation |

---

# Slide 6 — Data Preparation

## Data preparation performed for analysis

Before building the Tableau dashboard, the dataset can be organized around the following analytical fields:

### Date

Used for daily traffic analysis.

### Route

Used to compare airport connections and identify high-volume routes.

### No. of flight

Used as the primary measure for total and daily flight activity.

### Coordinates

Used to represent route connections geographically on the map.

### Airline

Used to understand airline participation in flight activity.

### Event

Used to compare the two event categories recorded in the source data.

### Data-quality note

Some fields contain missing values:

- Base Airline / Base Flight Number have missing records.
- Gate information also contains missing records.

These fields should therefore be used with appropriate filters or aggregation rather than assuming every flight has a value.

---

# Slide 7 — KPI Cards

## 1. Total Flight Events

### Value: **88,532**

This KPI represents the total number of flight events recorded in the dataset.

**Tableau concept:**

`SUM([No. of flight])`

### Why it matters

It provides an immediate view of the overall scale of airport activity during the selected period.

---

## 2. Routes

### Value: **271**

This KPI represents the number of distinct routes found in the dataset.

**Tableau concept:**

`COUNTD([Route])`

### Why it matters

It indicates the breadth of SFO's route connectivity within the analyzed data.

---

# Slide 8 — Top 5 Route Distance

## Purpose

The **Top 5 Route Distance** chart identifies the longest route connections associated with SFO.

The route distance is derived from the geographic coordinates contained in the dataset.

### Top 5 longest routes

| Rank | Route | Approx. distance (km) |
|---:|---|---:|
| 1 | BLR-SFO | 13,988 |
| 2 | SFO-SIN | 13,583 |
| 3 | SIN-SFO | 13,583 |
| 4 | SFO-DXB | 13,020 |
| 5 | DXB-SFO | 13,020 |

### Interpretation

The chart shows that the longest connections are mainly international routes.

The longest route in the dataset is **BLR-SFO**, followed by **SIN-SFO / SFO-SIN** and **SFO-DXB / DXB-SFO**.

### Business relevance

Long-distance routes are useful for understanding:

- International connectivity
- Geographic reach
- Long-haul operations
- Route network expansion

---

# Slide 9 — Top 5 Routes by Total Flights

## Purpose

This chart identifies the routes with the highest number of recorded flight events.

### Top 5 routes


| Route | Total flights |
|---|---:|
| SFO-LAX | 4,036 |
| LAX-SFO | 3,932 |
| JFK-SFO | 2,351 |
| SFO-JFK | 2,349 |
| SEA-SFO | 2,286 |

### Key observation

**SFO-LAX** is the highest-volume route in the dataset, followed by **LAX-SFO**.

Other high-volume routes include:

- JFK-SFO
- SFO-JFK
- SEA-SFO

### Business relevance

High-volume routes can be considered important connections for:

- Route demand analysis
- Capacity planning
- Schedule planning
- Airport connectivity monitoring

---

# Slide 10 — Airport Traffic Growth / Daily Flight Trend

## Purpose

The line chart shows the number of flight events recorded for each day in March 2020.

### Daily traffic range

- **Highest daily traffic:** 3,295 flights on 06 March 2020
- **Lowest daily traffic:** 1,970 flights on 26 March 2020
- **Monthly total:** 88,532 flight events

### Trend visible in the dashboard

The beginning of March shows daily activity around the **3,000+ flight-event level**.

Traffic then becomes lower during the later part of the month, with the lowest recorded daily value occurring on **26 March 2020**.

### Business relevance

Daily traffic analysis can help stakeholders monitor:

- Changes in airport activity
- High- and low-traffic days
- Operational planning
- Historical traffic patterns

> **Important:** This dashboard describes historical activity in March 2020. It should not be treated as a current SFO traffic forecast.

---

# Slide 11 — Route Map

## Total Routes in Map

The map visualizes the geographic connections represented in the dataset.

### Map uses

- Starting/ending route coordinates
- Route information
- SFO as the central airport connection
- Geographic distribution of domestic and international routes

### What the map helps show

The map makes it easier to identify:

- Domestic connections
- International connections
- Long-distance connections
- Multiple destinations served from SFO
- Overall route network coverage

### Examples visible in the dashboard

Routes include connections such as:

- LAX-SFO
- JFK-SFO
- SEA-SFO
- SIN-SFO
- HKG-SFO
- DEL-SFO
- DXB-SFO
- SYD-SFO
- MEL-SFO

---

# Slide 12 — Airline Analysis

## Airline contribution

The dataset contains airline-level flight-event information.

### Top airlines by recorded flight events

| Rank | Airline | Flight events |
|---:|---|---:|
| 1 | UA | 16,678 |
| 2 | NZ | 10,928 |
| 3 | AC | 8,052 |
| 4 | AS | 4,914 |
| 5 | LH | 3,187 |
| 6 | QF | 2,986 |
| 7 | DL | 2,878 |
| 8 | AA | 2,867 |
| 9 | CM | 2,771 |
| 10 | SQ | 2,635 |

### Key observation

**UA** has the highest number of recorded flight events in the detailed dataset.

Other major contributors include:

- NZ
- AC
- AS
- LH
- QF
- DL
- AA

### Business relevance

Airline analysis can help understand:

- Airline participation
- Relative flight activity
- Carrier concentration
- Potential dependency on major carriers

---

# Slide 13 — Flight Event Analysis

## Event categories

The dataset contains two values in the flight-event field:

| Event | Flight events |
|---|---:|
| A | 45,578 |
| D | 42,954 |

The two categories are recorded as **A** and **D** in the source data.

### Dashboard use

These event categories can be compared to understand how flight events are distributed between the two recorded event types.

> The dashboard should retain the source-system definitions for `A` and `D` when presenting this field. If the official data dictionary defines them as arrival and departure, those labels can be used in the final Tableau version.

---

# Slide 14 — Main Dashboard Insights

## Key findings visible from the analysis

### 1. Strong route connectivity

The dataset contains **271 unique routes**, showing a broad network connected with SFO.

### 2. SFO-LAX is the highest-volume route

The **SFO-LAX** route records the highest number of flight events at **4,036**, followed by **LAX-SFO** at **3,932**.

### 3. Long-haul international routes are among the longest

Routes involving Singapore, Bengaluru, Dubai, Melbourne, Delhi, and other international destinations create the longest geographic connections.

### 4. Traffic changes during March

Daily flight activity is higher at the beginning of March and falls substantially during the later part of the month.

### 5. Airline activity is concentrated

UA is the largest airline category by recorded flight events in the dataset.

### 6. Geographic visualization adds context

The route map makes the global reach of the SFO network easier to understand than a table alone.

---

# Slide 15 — Tableau Dashboard Design

## Dashboard components

The dashboard contains the following visual elements:

| Dashboard element | Purpose |
|---|---|
| Total Flight Events KPI | Shows total flight activity |
| Routes KPI | Shows unique route count |
| Top 5 Route Distance | Shows longest route connections |
| Top 5 Routes Total Flights | Shows busiest routes |
| Airport Traffic Growth line chart | Shows daily traffic trend |
| Total Routes in Map | Shows geographic route connectivity |
| SFO airport image/title | Provides dashboard identity and context |

### Design approach

The dashboard uses a clean executive-reporting layout:

- KPI cards at the top
- Comparison charts in the middle
- Trend analysis on the lower-left
- Geographic map on the lower-right

This layout allows users to move from **overall KPIs → route comparison → traffic trend → geographic analysis**.

---

# Slide 16 — Recommended Tableau Filters

## Suggested interactive filters

The dashboard can be enhanced with filters such as:

### Date
Allow users to select specific dates or date ranges.

### Airline
Allow comparison of flight activity across airlines.

### Route
Allow users to focus on individual routes.

### Event
Allow comparison between the available event categories.

### Gate
Useful for operational-level analysis when gate information is available.

These filters can make the dashboard more useful for detailed exploration without changing the main dashboard structure.

---

# Slide 17 — Analytical Methodology

## Analysis flow

```text
Raw SFO Flight Data
        ↓
Data Cleaning & Validation
        ↓
Date / Route / Airline / Event Preparation
        ↓
KPI Calculations
        ↓
Route & Distance Analysis
        ↓
Daily Traffic Trend
        ↓
Geographic Route Mapping
        ↓
Tableau Dashboard
        ↓
Business Interpretation
```

### Main measures

- Total flight events
- Distinct route count
- Flight events by route
- Flight events by airline
- Daily flight events
- Route distance
- Flight events by event category

### Main dimensions

- Date
- Route
- Airline
- Base Airline
- Event
- Gate
- Geographic coordinates

---

# Slide 18 — Data Quality and Limitations

## Important limitations

1. **Time period is limited to March 2020.**  
   Therefore, the analysis represents a specific historical period.

2. **Missing values exist.**  
   Base airline, base flight number, and gate fields contain missing records.

3. **Flight-event count is not the same as passenger count.**  
   `No. of flight` represents recorded flight events, not the number of passengers.

4. **Route distance is geographic distance.**  
   A calculated distance between coordinates should not automatically be interpreted as the exact aircraft flight path.

5. **Historical analysis is descriptive.**  
   The dashboard explains what happened in the dataset; it does not predict future airport traffic.

---

# Slide 19 — Business Recommendations

## Recommendations based on the dashboard structure

### Route management
Monitor high-volume routes such as SFO-LAX and LAX-SFO for capacity and scheduling analysis.

### International connectivity
Review long-distance international routes to understand SFO's global network coverage.

### Traffic monitoring
Track daily flight-event changes to identify periods of unusually high or low activity.

### Airline analysis
Compare airline-level activity to understand the distribution of airport operations across carriers.

### Dashboard monitoring
Use Tableau filters to investigate route, airline, date, and event-level changes.

> These are analytical-use recommendations based on the dashboard structure, not operational decisions or forecasts.

---

# Slide 20 — Project Conclusion

## Conclusion

The SFO Airport Analysis Tableau project provides a consolidated view of airport flight activity during March 2020.

The dashboard combines:

- **88,532 flight events**
- **271 unique routes**
- Route-volume analysis
- Long-distance route analysis
- Daily traffic trend
- Airline-level analysis
- Geographic route mapping

The project demonstrates how Tableau can convert detailed airport flight records into an interactive business dashboard that supports historical airport traffic and route-network analysis.

---

# Slide 21 — Project Tools

## Technologies used

### Excel
Used as the source dataset and for reviewing the structured flight data.

### Tableau
Used for:

- Data connection
- Data preparation
- Calculated fields
- KPI cards
- Charts
- Maps
- Dashboard design
- Interactive analysis

### Analysis approach

The project focuses on **descriptive and diagnostic analysis**.

No machine-learning model or predictive model is required for this dashboard.

---

# Slide 22 — Portfolio / Resume Description

## Short project description

**San Francisco SFO Airport Analysis — Tableau**

> Developed an interactive Tableau dashboard using SFO airport flight-event data from March 2020. Analyzed 88K+ flight events and 271 unique routes to understand airport traffic trends, busiest routes, long-distance connections, airline activity, and geographic route coverage. Created KPI cards, route comparison charts, a daily traffic trend, and a geographic route map to present the analysis in a business-friendly format.

---

# Slide 23 — Final Dashboard Summary

## Dashboard Story

```text
SFO Airport Activity
        ↓
How much flight activity?
        ↓
88,532 Flight Events
        ↓
How broad is the network?
        ↓
271 Routes
        ↓
Which routes are busiest?
        ↓
SFO-LAX / LAX-SFO / JFK-SFO / SFO-JFK / SEA-SFO
        ↓
Which routes are longest?
        ↓
BLR-SFO / SIN-SFO / SFO-SIN / SFO-DXB / DXB-SFO
        ↓
How did traffic change?
        ↓
Daily traffic decreased during the later part of March
        ↓
Where are the routes?
        ↓
Global route map centered around SFO
```

---

# Appendix — Key Dataset Statistics

| Metric | Value |
|---|---:|
| Detailed records | 88,532 |
| Total flight events | 88,532 |
| Unique routes | 271 |
| Analysis dates | 31 |
| Start date | 01 March 2020 |
| End date | 31 March 2020 |
| Unique airlines | 65 |
| Unique base airlines | 31 |
| Unique gates | 97 |
| Event categories | 2 |
| Geometry type | MultiPoint |

---

# Appendix — Top Route Reference

| Rank | Route | Flight events |
|---:|---|---:|
| 1 | SFO-LAX | 4,036 |
| 2 | LAX-SFO | 3,932 |
| 3 | JFK-SFO | 2,351 |
| 4 | SFO-JFK | 2,349 |
| 5 | SEA-SFO | 2,286 |
| 6 | SFO-SEA | 2,023 |
| 7 | LAS-SFO | 1,855 |
| 8 | ORD-SFO | 1,764 |
| 9 | SFO-ORD | 1,759 |
| 10 | SFO-LAS | 1,754 |

---

# Appendix — Project Deliverables

### Deliverable 1 — Dataset
`AIRPORT ANALYSIS(3).xlsx`

### Deliverable 2 — Tableau Dashboard
San Francisco SFO Airport Dashboard

### Deliverable 3 — Documentation
This Markdown documentation file.

---

## End of Documentation

**Project:** San Francisco SFO Airport Analysis  
**Tool:** Tableau  
**Domain:** Airport / Aviation Analytics  
**Data period:** March 2020
