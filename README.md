# IPL Cricket Match Analysis (2008 to 2019)

In this project I analyzed 12 seasons of IPL data to look at team performance, the effect of the toss, venues and the top players. The analysis is done in Python using pandas, Matplotlib and Seaborn.

## Dataset

The project uses two files from the IPL Complete Dataset:

* **matches.csv** has one row per match (756 matches) with the season, teams, toss, venue, result, winner and player of the match.
* **deliveries.csv** has one row per ball (179,078 rows) with the batsman, bowler, runs, extras and dismissals.

## Data cleaning

* Fixed team names that were spelled two ways (Rising Pune Supergiant and Rising Pune Supergiants). Delhi Daredevils and Delhi Capitals were treated as one team since it is the same franchise renamed in 2019.
* Fixed venue names that appeared under different spellings, for example M Chinnaswamy Stadium and M. Chinnaswamy Stadium. Also changed Bengaluru to Bangalore.
* The missing winner and player of the match values were only in the 4 no result games, so they were filled as "No Result" and "No Award".
* All 7 missing cities were at Dubai International Cricket Stadium, so they were filled as Dubai.
* Dropped the umpire3 column because 84% of it was empty.
* Dates for 2018 and 2019 were in a different format from the other seasons, so they were all converted to one date format.
* Some super over balls were not flagged, so I fixed the flag and left super overs out of career runs and wickets.
* Removed 22 repeated deliveries. A repeated ball was only removed if its over ended up with more than 6 legal balls, since one of the repeats was actually a real ball with a wrong ball number.

## Key findings

* Mumbai Indians won the most matches (109), but Chennai Super Kings had the best win percentage (60.98%).
* The toss winner won the match only 52.3% of the time, so the toss gives a very small advantage.
* After winning the toss, teams chose to field first 460 times and bat first 292 times.
* M Chinnaswamy Stadium hosted the most matches (80), followed by Eden Gardens (77).
* V Kohli scored the most runs (5,429) and SL Malinga took the most wickets (170).

## How to run

Install the libraries:

```
pip install pandas numpy matplotlib seaborn jupyter
```

Then open the notebook in the notebooks folder. The file paths in the notebook point to Kaggle, so change them to the data folder if you run it on your own computer.

## Tools

Python, pandas, NumPy, Matplotlib, Seaborn and Jupyter Notebook.
