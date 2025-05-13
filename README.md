# Chess-Games-Analysis-with-Power-BI

### Project Goals

* To gain insights into chess game patterns and player performance using data visualization and analysis techniques in Power BI.
* To identify factors that contribute to winning or losing a chess game.
* To explore relationships between player ratings, openings, game outcomes, and other relevant variables.
* To create an interactive Power BI dashboard that allows users to explore the data and draw their own conclusions.

###  Data Source

* The dataset is a set of just over 20,000 games collected from a selection of users on the site Lichess.org. The chess ratings of the users range from 784 to 1883. This dataset contains information about chess games, including player details, game results, moves, openings, and opening ply (number of moves in the opening phase). 

### Project Scope

* **Data Acquisition and Preparation:**
    * Downloaded the chess games dataset from Kaggle.
    * Using Power Query in Power BI, some columns deemed unnecessary for data analysis are deleted. Also, the opening names are modified so that the opening variations are not included. 
      A new column (rated game) is also created to convert boolean values (true and false) into 'yes'  and 'no'.
       
       ![CgamescolsPNG](https://github.com/user-attachments/assets/8c5eeab7-73b5-40c7-a2ce-ba20ba5e4a8c)

                                        Original Columns

      ![ChesscolsPNG](https://github.com/user-attachments/assets/e30ef019-0419-4ecc-8cbf-9834a7bcd7f5)

                                        Final Columns
    
* **Data Analysis and Visualization:**
    * Explore the dataset to understand its structure and content.
    * Create visualizations to analyze various aspects of the games, such as:
        * Win/loss/draw distribution (doughnut chart)
        * Player rating distribution and performance (KPI card) 
        * Popularity of different openings (KPI card, treemap, and funnel chart)
        * Impact of time control on game results (matrix chart)
        * Impact of playing white pieces on game results (KPI card)
    * Use DAX to calculate the following:
        * HigherRatedWinCount = 
SUMX(
    games,
    IF(
        games[victory_status] IN {"mate", "resign", "outoftime"} &&
        (
            (games[black_rating] > games[white_rating] && games[winner] = "black") ||
            (games[white_rating] > games[black_rating] && games[winner] = "white")
        ),
        1,
        0
    )
)
        * white_win_count = 
SUMX(
    games, 
    IF(
        SEARCH("white", games[winner], 1, 0) > 0, 
        1, 
        0
    )
)
        * Higher Rated Win Percentage = DIVIDE(games[HigherRatedWinCount],games[Total Games])
        * White Win Percentage = DIVIDE(games[white_win_count],games[Total Games])

* **Potential Analysis Areas:**
    * Opening Analysis: Which openings are most common? Which have the highest win rates for white/black?
    * Player Performance: How do player ratings correlate with win rates? Are there differences in performance between different rating levels?
    * Game Characteristics: How does the length of a game affect the outcome? How often do games end in draws?
    * Temporal Analysis: Are there any trends in game outcomes or player ratings over time?
    * Impact of Game Settings: How does the time control affect the game outcome?

### Tools and Technologies

* Power BI Desktop
* Power Query (for data transformation)
* Kaggle (for data source)

### Insights 

* The players with the white pieces win 50% of the games, and the players with black pieces win 45% of the games, and 5% of the games are drawn.
* The players with the higher rating win 62% of the games, regardless of the time control.
* The average opening ply, which is a measure of opening popularity, is only 5%.

### Recommendations

* Addressing the White vs. Black Win Rate Discrepancy:

Recommendation: Players whould dedicate more study time to understanding solid and active responses to common White openings. Analyze lost games as Black to identify recurring problems in the opening or early middlegame. Explore different opening systems for Black to find those that suit own style and yield better results.

* Leveraging the Rating Advantage:

Recommendation: Focus on consistent, high-quality play to capitalize on rating advantage. Since higher-rated players win 62% of the time regardless of time control, prioritize making sound strategic and tactical decisions in every game. Avoid unnecessary risks or overly complex lines that could negate your rating advantage. Analyze losses against lower-rated players to identify potential complacency or specific weaknesses they exploited.

* Addressing the Low Average Opening Ply:

Recommendation: Expand understanding of opening theory and strategic ideas beyond the first few moves. While memorizing long variations isn't always necessary, understanding the fundamental plans, typical pawn structures, and piece placements associated with various openings for both White and Black will give a player a significant advantage in the middlegame and endgame. Explore resources like opening databases, books, and video series to broaden your opening repertoire and understanding.

* Overall Improvement Strategy:

Recommendation: Combine opening study with middlegame and endgame practice. While addressing the Black win rate and opening knowledge is crucial, don't neglect the other phases of the game. Ensure training regimen includes tactical puzzles, strategic analysis, and endgame exercises to become a well-rounded player.

Recommendation: Analyze your games regularly, especially losses. Use engine analysis as a tool to identify critical mistakes and missed opportunities. Focus not just on tactical blunders but also on strategic errors in planning and piece placement. Understanding why you lost is more valuable than simply knowing what the losing move was.

Recommendation: Consider the psychological aspect of playing with Black. Knowing that statistically Black has a slightly lower win rate might subconsciously affect your mindset. Focus on playing actively and creating imbalances from the start to counter this inherent disadvantage.

Recommendation: Review drawn games to identify missed winning opportunities. While draws are a part of chess, analyzing these games can reveal situations where you might have been able to convert a favorable position into a win.

 
