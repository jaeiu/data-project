# 📘 Super Mario 64 Speedrun Dataset (Combined Categories)

A comprehensive dataset of **Super Mario 64 (SM64)** speedruns collected from the public leaderboards on [Speedrun.com](https://www.speedrun.com).  
This project consolidates the top runs across multiple categories into a single, structured Excel file for easier analysis, research, and visualization.

## 📂 File Included
- **`sm64_combined_runs.xlsx`** — A combined dataset containing the top 100 runs of each category on 16/02/2026.

___

## 🎯 Objectives

This dataset aims to:

- Provide a clean, unified dataset of SM64 leaderboard entries from multiple categories.
- Enable statistical and data‑driven analysis of SM64 speedrunning performance.
- Allow comparisons across categories, platforms, countries, and players.
- Support research, visualization projects, machine learning experiments, and community tools.
- Serve as a historical record of top leaderboard data across multiple SM64 categories.

___

## 🏁 Categories Included

The dataset contains leaderboard entries for:

- **120 Star**
- **70 Star**
- **16 Star**
- **1 Star**
- **0 Star**

Each category typically includes the top 100 runs from the Speedrun.com leaderboards.

___

## 📄 Dataset Structure

Each row represents a single speedrun. Below is a description of every column included:

| Column Name               | Description |
|---------------------------|-------------|
| `category`                | Run category (e.g., 120 Star, 70 Star, etc.) |
| `place`                   | Leaderboard placement (1 = world record at the time) |
| `player_name`             | Speedrunner’s username |
| `player_country`          | Country recorded on their Speedrun.com profile |
| `platform`                | Hardware/emulator used (`N64`, `EMU`, `VC`, etc.) |
| `verified`                | Whether the run was officially verified |
| `primary_time_seconds`    | Primary leaderboard time in seconds |
| `primary_time_formatted`  | Primary time (HH:MM:SS) |
| `real_time_seconds`       | Real-time tracking value in seconds |
| `real_time_formatted`     | Real-time in HH:MM:SS |
| `speedrun_link`           | Direct link to the run on Speedrun.com |
| `id`                      | Unique Speedrun.com run ID |

___

## Basic information
This dataset was found here: [Kaggle Dataset](https://www.kaggle.com/code/mcpenguin/super-mario-64-speedruns-data-collection "Kaggle Dataset") </p>
The data lists every player, country, time, platform, etc. Separated into 5 different Excel files for each category
## Tools used
- VSCode/Python
- Excel
- Tableau
___
## ⚠️ Limitations

- Data reflects the state of Speedrun.com at the time of extraction.
- Some entries include:
  - Missing country data (Unknown)
  - Unverified runs
- Only leaderboard entries present at the time of scraping are included.
- URL formats and player profiles may change.
___

## 🚀 Getting Started

### Load the dataset in Python
```python
import pandas as pd

df = pd.read_excel("sm64_combined_runs.xlsx")
df.head()
```
___
## Data Cleaning
### Python
[Here](https://github.com/jaeiu/data-project/blob/main/removing%20columns%20in%20star%20data.ipynb), I dropped unnecessary columns and then limited my table to the top 100 players, as it would give me more reliable data for the top players. In speedrunning, some people try to take as long as possible to beat a game, rather than as fast as possible.
![alt text](https://github.com/jaeiu/data-project/blob/main/project%20screenshots/python%20screenshot.png "Python Screenshot")
### Excel
The first commit was formatting and generalising the categories (England, Wales -> UK, Quebec -> Canada, etc.) found here: [Link](https://github.com/jaeiu/data-project/tree/main/Full%20Clean%20Data) </p>
Then I combined the different files into one with 5 sheets. Found here: [Link](https://github.com/jaeiu/data-project/blob/main/Star%20Table%20Data.xlsx) </p>
Finally, I put all categories into one sheet to make it easier for the data to follow in Tableau. Found here: [Link](https://github.com/jaeiu/data-project/blob/main/sm64_combined_runs%20(1).xlsx)
![alt text](https://github.com/jaeiu/data-project/blob/main/project%20screenshots/combined%20category%20excel.png)
___
# Data Example
## Data Insights 
All insights can be found in dashboard form here: [Tableau Dash](https://github.com/jaeiu/data-project/blob/main/M64%20Project%20Dash.twb)
### Time Distribution per Platform V Users per Platform
The images show that because the N64 has the highest amount of users, the total time distributed through the runs is also the highest of the 3 platforms.</p> 
This is in contrast to the emulators' times, as although they have fewer users, the drastic difference in total time would most likely be due to the consistent loads, which allow runs to have fewer random factors for runners to encounter.</p> 
Meanwhile, the Virtual Console has the smallest community and a moderate spread, given the playerbase, which could be due to the obscurity of the platform, due to not having any upside. 

<p align="center">
  <img width="45%" src="https://github.com/jaeiu/data-project/blob/main/project%20screenshots/users%20per%20platform.png" />
  <img width="45%"  src="https://github.com/jaeiu/data-project/blob/main/project%20screenshots/time%20distribution%20per%20platform.png" />
</p>

### Fastest Time per Category & Top Players per Category
If you look at the Fastest time in each category, then the top players of each category, you'll see that each record is held by the same person, Suigi, which shows exceptional consistency at the highest level of speedrunning. </p>
In 0 and 1 Star, they are glitch-based and precision-heavy, which is why they are both extremely fast, following *mostly* the same routing, which is why runners will overlap heavily in both categories. </p>
In 16 Star, routing starts to matter much more as players such as Slipperynip and GTM, who specialise in mid-game routing and BLJs, start to appear. The appearance of Finnii602 also shows that VC is viable in mid-star runs. </p>
For 70 Star, Movement starts to matter much more as the amount of glitches necessary to complete the run decreases significantly, which is shown as movement-heavy players, such as Taihou, appear. This category rewards players who have long-form consistency rather than pure glitch execution. </p>
For 120 Star, this category is the highest consistency tester, with the record being 1:35:28. Each run is like a marathon, testing movement optimisation and endurance, which rewards highly disciplined and consistent players instead of glitch specialists.

<p align="center">
  <img width="45%" src="https://github.com/jaeiu/data-project/blob/main/project%20screenshots/time%20per%20category.png">
  <img width="45%" src="https://github.com/jaeiu/data-project/blob/main/project%20screenshots/top%205%20per%20category.png"> 
</p>

## 🎯 Cross-Category Insights
### A. Player Overlap Shows Strengths
- Suigi: complete dominance — elite in both glitch and full-game routes.
- Weegee: highly versatile — appears in almost every category’s top 5.
- Karin, Finnii602, taihou: movement-heavy specialists, shine in mid-high star categories.

### B. Platform Influence
From earlier analysis:
- N64 players dominate top positions (lowest input latency).
- EMU players tend to cluster slightly lower when categories depend heavily on movement rather than resets.
- VC appears mainly in mid-star categories (16, 70).

### C. Variability by Category
- 0/1 Star: Ultra-tight; milliseconds matter.
- 16 Star: Strong glitch specialists do well.
- 70 Star: Movement optimisation becomes king.
- 120 Star: Only very consistent runners can reach top 5.


## 📜 License & Attribution
This dataset consists solely of public leaderboard metadata from Speedrun.com.

- Please cite Speedrun.com when using the dataset.
- No copyrighted video or private data is included.
- Runner usernames and metadata remain the property of their respective owners.


## ❤️ Acknowledgements
Huge respect to the **SM64 speedrunning community**, moderators, and all runners whose data appears here. </p>
If you build anything cool using this dataset, feel free to share it!


