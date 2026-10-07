# Premier League Team Styles Analysis

## Objective

This project uses data analysis and machine learning to identify broad statistical profiles among Premier League teams.

The goal is to explore whether teams can be grouped based on their attacking output, defensive performance, shot volume, corners and disciplinary activity.

## Dataset

- Competition: Premier League
- Season: 2025/26
- Matches: 380
- Source: Football-Data.co.uk

## Features

The analysis uses the following team-level per-match metrics:

- Goals per match
- Goals conceded per match
- Shots per match
- Shots on target per match
- Corners per match
- Fouls per match
- Yellow cards per match
- Red cards per match

## Methodology

1. Match-level data was collected from Football-Data.co.uk.
2. Home and away statistics were combined to create team-level totals.
3. Statistics were converted to per-match metrics.
4. Features were standardised using `StandardScaler`.
5. PCA was used to reduce the eight features to two principal components for visualisation.
6. K-Means clustering was used to group teams based on their statistical profiles.
7. The number of clusters was evaluated using the Elbow Method and Silhouette Score.
8. Cluster stability was tested across multiple random seeds.

## Model Selection

The Silhouette Score was compared across different numbers of clusters.

The 3-cluster solution produced the strongest silhouette score:

- 2 clusters: 0.281
- 3 clusters: 0.286
- 4 clusters: 0.235
- 5 clusters: 0.221

The 3-cluster solution was therefore selected for the final analysis.

The average silhouette score across multiple random seeds was approximately 0.28, indicating that the clusters provide useful broad groupings but also have some overlap.

## Results

### 1. High-Output / Strong Performance

Teams:

- Arsenal
- Aston Villa
- Liverpool
- Manchester City
- Manchester United
- Newcastle

Profile:

- Highest goals per match
- Highest shot volume
- Highest shots on target
- Strong defensive record
- Lower disciplinary activity

### 2. Aggressive High-Activity

Teams:

- Bournemouth
- Brighton
- Chelsea
- Tottenham

Profile:

- High shot and corner activity
- Relatively high fouls and yellow cards
- Strong attacking involvement
- More balanced attacking and defensive output

### 3. Lower-Output / Struggling

Teams:

- Brentford
- Burnley
- Crystal Palace
- Everton
- Fulham
- Leeds
- Nottingham Forest
- Sunderland
- West Ham
- Wolves

Profile:

- Lower goals and shot volume
- Lower shots on target
- Higher goals conceded
- Lower corner production

## Key Finding

The clustering shows that teams can be separated into broad statistical profiles using relatively simple match statistics.

Manchester United, for example, falls into the High-Output / Strong Performance cluster because of its high attacking activity and goal output. This classification should not be interpreted as a definitive judgement of overall team quality.

## Limitations

This analysis has several limitations:

- Only one Premier League season was analysed.
- The dataset contains relatively basic match statistics.
- Advanced metrics such as xG, possession, progressive passes and pressing intensity were not included.
- K-Means clusters are statistical groupings rather than definitive tactical identities.
- The relatively modest silhouette score indicates meaningful overlap between some teams.

## Future Improvements

Future versions could include:

- Expected goals (xG)
- Possession
- Passing metrics
- Progressive passes
- Pressing metrics
- Defensive actions
- Multi-season data
- Player-level analysis
- Formation and tactical information

## Tools

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Google Colab
- GitHub
