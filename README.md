# Chess-Games-Analysis-with-Power-BI

### Project Goals

* To gain insights into chess game patterns and player performance using data visualization and analysis techniques in Power BI.
* To identify factors that contribute to winning or losing a chess game.
* To explore relationships between player ratings, openings, game outcomes, and other relevant variables.
* To create an interactive Power BI dashboard that allows users to explore the data and draw their own conclusions.

###  Data Source

* The dataset is a set of just over 20,000 games collected from a selection of users on the site Lichess.org. This dataset contains information about chess games, including player details, game results, moves, openings, and opening ply (number of moves in the opening phase). 

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
        * Win/loss/draw distribution
        * Player rating distribution and performance
        * Popularity of different openings
        * Impact of time control on game results
        * Impact of playing white pieces on game results
    * Use Power BI's features to create interactive dashboards with slicer. 
* **Key Metrics and Analysis:**
    * Player win rates
    * Opening success rates (White vs. Black)
    * Average game length
    * Most common game termination methods (e.g., checkmate, resignation)
    * Correlations between player ratings and game outcomes
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

 
