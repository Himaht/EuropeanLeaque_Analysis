# European Football Analysis (Ongoing)

This project analyzes **Player Standard Stats (2023–2024)** from the **Big 5 European Leagues** using Python.  
It focuses on data scraping, cleaning, feature engineering, and basic analytics to extract meaningful insights from football player performance data.

🚧 **Status:** Ongoing — features and analyses are actively being added.

---

## 📌 Project Overview

The project ingests player statistics from an HTML source, cleans and structures the data, and performs analytical tasks such as:

- Identifying top scorers and playmakers
- Handling mid-season player transfers
- Computing derived performance metrics
- Assessing data quality issues like missing values and duplicates

The goal is to build a reusable and extensible analysis pipeline for football performance data.

---

## 🛠️ Technologies Used

- **Python**
- **pandas**
- **NumPy**
- **BeautifulSoup**
- **Matplotlib**
- Jupyter / Google Colab

---

## 📂 Current Features

### Data Ingestion
- Scrapes *Player Standard Stats* table from an HTML file
- Automatically ignores unrelated tables

### Data Cleaning
- Converts numeric columns from strings to numbers
- Handles missing values
- Extracts:
  - League name
  - 3-letter country code for nationality
  - Primary playing position
- Removes duplicate columns

### Derived Metrics
- Minutes per Game
- Goal Contribution Rate (Goals + Assists per 90)

### Player Analysis
- Top scorer
- Top playmaker
- Ironman (most minutes played)
- Most efficient striker (goals per minute)
- Most disciplined player (cards per 90)

### Transfer Handling
- Identifies players appearing for multiple clubs
- Aggregates total stats for transferred players

### Data Quality Checks
- Reports missing values per column
- Flags duplicate player entries

---

## ▶️ How to Run

```python
efa = EuropeanFootballAnalysis()
efa.scrape()
efa.clean_data()
efa.add_derived_metrics()

efa.find_top_scorer()
efa.find_playmaker()
efa.find_ironman()
efa.find_efficient_striker()
efa.find_most_disciplined()
missing, dup_players = efa.data_quality_report()
missing, dup_players.head()
