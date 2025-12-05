Does Home Field Matter? Exploring Shots and Accuracy in Bundesliga Matches
================
by Lauren, Maeve, Annika

## Summary

For our project, we chose to look at data from the 2024-2025 season of Bundesliga, a German soccer league with eighteen teams. Our dataset contains statistics from 306 games with variables for the home and away teams, including corner kicks taken, shots, shots on target, fouls, and yellow cards. We chose to use this dataset because it is well organized and required very minimal “cleaning up” before being used in our code. We chose to explore how playing at Home versus Away impacts team performance. To answer this question, we looked specifically at the average shots taken, shots on target, and fouls received for the home and away teams in each match, using a different style of graph for each variable. Each graph was created using ggplot and other tools we learned in class. We frequently utilized the mutate, group_by, and summarise functions to build our graphs because most of our visualizations included average values or were grouped by the “home” or “away” variable.
	
To address the part of our research question that examines team performance, measured by average shots taken, we created a horizontal side-by-side bar chart that shows each team's average home and away shots per game. The visualization reveals that overall, teams take more shots while playing at home than they do when playing away. Of the eighteen teams in our dataset, fifteen have an increased average number of shots per game while playing at home. This suggests a home-field advantage and that teams might play more offensively at home. 
	
Our next graph was a boxplot comparing the shots on target taken by the home and away teams. The home teams plot shows a higher median value, however the larger box signifies less consistency and greater variation in home team performance compared to the away team. Overall, the distribution suggests that while home teams tend to create more scoring opportunities, their success rate varies more across the season, as shown by the greater distance between the lower and upper quartiles.
	
Another visualization we created to explore our research question was a dumbbell plot displaying each team’s average fouls received while playing at home versus away. The gray bar of each dumbbell shows the difference between each team’s average fouls when playing at home or away. Of the eighteen teams in our dataset, eleven tend to receive more fouls while playing away. This might indicate that away teams play more defensively due to increased pressure. The relationship points to a potential home-field advantage since home teams tend to receive fewer fouls than away teams. 
	
In addition to our three plots included on the handout, we created a pie chart displaying the total yellow cards received across the 2024-2025 season by the home teams and away teams. Although the visualization appears in our memo, we chose not to include it in the handout since we felt it was not the best type of visualization or use of our data to showcase while examining our research question. The pie chart shows that the away teams received more yellow cards than the home teams during the season, suggesting that away teams might play more offensively and aggressively, thus leading to more disciplinary action against them. 
	
Our final graph is a faceted scatter plot showing the average corner kicks per team when they are home versus away. When at home, the team Leverkusen averaged more corner kicks per game than any other home team, and the team Bayern Munich had the highest average among away teams. Interestingly, both of these teams were among the top performers in the league in the 2024-2025 season. The graph also compares the overall average for home and away corner kicks, showing that the average amount of corner kicks taken at home was about 1.5 more than away. This contributes to our conclusion that home teams have an advantage on the field because they have more scoring opportunities from their higher average of corner kicks taken.
	
Based on our findings, illustrated by our data visualizations, we assert that there is a strong home-field advantage in the 2024-2025 Bundesliga League. Team performance, as measured by average shots taken, shots on target, and fouls received, favors teams when they play on home turf. Our side-by-side bar chart shows that home teams take more shots on average than away teams, our boxplot shows that home teams take more shots on target than away teams, and our dumbbell plots show that away teams receive more fouls than home teams. We contend that team performance is likely stronger on home turf due to familiarity with the environment and support from the home crowd. We recognize the substantial limitations of our research, as we examined only a single season in a single soccer league. If we were to conduct further research, we would explore the trends of these variables and additional variables over a longer period and across many seasons to determine a more comprehensive, definitive relationship between home-field advantage and team performance.\

## Handout

Our handout can be found [here](handout/handout.pdf). You can update the filename and extension of your handout, currently it is called handout.pdf

## Memo

A link to the code and how we created our graphics in our memo can be found [here](memo/memo.md).

## Data

Football-Data.co.uk 2024, Bundesliga Season 2024–25 Dataset, raw dataset. Data originally published by Football-Data.co.uk; accessed via the datasets/football-datasets GitHub repository on October 14, 2025:
https://github.com/datasets/football-datasets/blob/main/datasets/bundesliga/season-2425.csv

## References

Stalder, Tobias, and Y. Holtz. “Extended Dumbbell Plot in R with ggplot2.” *R Graph Gallery*, 2021, r-graph-gallery.com/web-extended-dumbbell-plot-ggplot2.html. Accessed 14 Oct. 2025.

datasets project (GitHub). *Football-Datasets: Bundesliga*. GitHub, github.com/datasets/football-datasets/tree/main. Accessed 14 Oct. 2025.  

Football-Data.co.uk. *Football-Data.co.uk Football Match Data*. Accessed 14 Oct. 2025. www.football-data.co.uk. 

