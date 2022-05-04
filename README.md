# brownlow_medal_analysis
Analysing whether strong performance in individual statistical categories correlated with success in the Brownlow Medal. With this being my first attempt at producing a case study, I'm looking to outline the process I followed as well as the data I uncovered.

The Brownlow Medal is awarded to the AFL player considered the 'best and fairest' player during the home and away season. The medal is voted on collectively by the three on-field umpires, who award votes to whom they consider to be the 3 players on the ground who best fit the voting criteria. The votes are awarded under a 3-2-1 system, i.e. 3 votes, 2 votes and 1 vote are awarded to the players the umpires considered the 'best and fairest', second best and third best in the game respectively.

Using the data provided in the .CSV files above, I set out to identify in which individual statistical categories (i.e. contested possessions, disposals, goals, tackles etc), strong performance by players positively correlated with success in the Brownlow Medal between the years 2012 & 2021.

EXPLORING THE DATA

I decided to begin by reviewing the statistical performance of the Brownlow medalist from each year. Using the below SQL query, I was able to locate the Brownlow Medal winners for each year.

<img width="775" alt="brownlow winners query" src="https://user-images.githubusercontent.com/82799348/166616865-48f03358-aefd-424b-803b-52117d30b7b7.png">

Using this query, I created new table with the Brownlow winners information. Using this table, I built a query to find the AVG number of disposals by the player in their Brownlow medal winning year and how that compared with the AVG number of disposals by the top 50 ranked players by disposal AVG from that same season. I was able to include the difference between these two AVGs, as well as the rank of the Brownlow winning player in the AVG disposal category for that year. The query and resulting table are included below:

<img width="1128" alt="brownlow disposal comparision sql " src="https://user-images.githubusercontent.com/82799348/166616942-341a312f-64bc-4cb4-8080-932594909155.png">

![brownlow disposal comparision](https://user-images.githubusercontent.com/82799348/166616998-b41223a5-248b-4ea8-8b93-084ae7c6fe73.png)

Once the initial query structure was set up, I was able to add other player statistics to the table by mirroring the existing design and making the changes as needed for the new statistics category. The resulting table is available in the files as brownlow_master_comparison.csv and the final SQL query is available as brownlow_master_comparision_query.

From this initial exploration, I was able to discover that the Brownlow medalist consistently ranks in the top 10 in disposals, clearances and contested possession statistics. The Brownlow medalist rank was also typically quite high in the in50 and uncontested possession stats, although with some variance, whilst rankings in some stats such as goals and tackles appeared to have very little influence on the Brownlow medalist at all.

VISUALISING THE DATA

With this information in mind, I decided to move my analysis to Tableau in order to demonstrate the relationship between the statistics and Brownlow success visually.

I decided to make a scatterplot for each statistic, with the total Brownlow Votes on the y-axis, and the statistic on the x-axis. In order to visually demonstrate the overlap between the two axis, I added a shaded area to indicate which players finished in the Top 10 for either or both categories.

After completing the visualisations I was able to identify some trends in the data and recognise in which categories strong performance correlated with success in the Brownlow Medal. Originally, the visualisations were saved on Tableau Public with the statistics grouped by year. I decided to change this to a ‘year on year’ view in the key stats, in order to demonstrate the YoY trends in each statistic more clearly.

This initial visualising of the data more or less confirmed what the initial SQL query appeared to show; that the top performers in statistics such as contested possessions & disposals typically are the higher performers in the Brownlow medal, whilst strong performance in statistics such as rebound 50s and goals appear to have little to no positive correlation with Brownlow medal performance at all.

There were, however, a number of outliers in the key stat categories. For example, Players who performed quite well in the disposals statistic but poorly in the Brownlow medal. I decided to explore why this was the case, to understand if there were any other factors that may have contributed to their lack of votes.

In particular, I reviewed two outliers from the 2012 disposals worksheet highlighted below. 

![tg:mb 2012 highlighted](https://user-images.githubusercontent.com/82799348/166617156-39b0d436-6455-4d78-8040-94536d460683.png)

Using SQL, I was able to determine that both of these players ranked highly in other statistics whilst still performing poorly in the Brownlow medal as per the below table.

![sql tg:mb 2012](https://user-images.githubusercontent.com/82799348/166617187-d33c9518-1a1b-4ca4-adbc-890f58914b8f.png)

I decided to dig deeper into the performance of the teams that these players represented, as individually their statistical performance is similar to other players who received many more votes than they did. Using the below query I was able to determine that both of these players were involved in games where they were consistently in the losing team, and usually by a large margin.

![points diff tg:mb 2012](https://user-images.githubusercontent.com/82799348/166617217-aad7e5e4-a4db-4b4d-a99f-a0c884f9a3ef.png)

I decided to build a visualisation in Tableau which compared Brownlow performance with total wins and average margin. It was clear from this process that team performance was another important factor in an individual players Brownlow medal performance.

For each of the individual statistic visualisations, two filters were applied to remove significant outliers. For example, votes in the Brownlow medal are awarded on a game by game basis, meaning that a player who only played a handful of games, regardless of their performance, is limited to the amount of votes they can receive depending on how many games they played. The below image is an example of this, with no player playing less than 17 games in 2015 receiving more than 10 votes.

<img width="894" alt="games played 2015 example" src="https://user-images.githubusercontent.com/82799348/166617619-f2e1a553-d7c7-4cac-b674-19a275524108.png">

In order to combat this, a filter with a minimum of 15 games played in each season was applied to the visualisations to further refine the results.

Additionally, the top 150 performers in each statistic by their yearly averages are included in each visualisation. The idea being that in order to determine whether a strong performance in a certain statistic positively correlated with performance in the Brownlow medal, the best performers from that statistic should be the group analysed.

CONCLUSION

From the analysis completed thus far, I was able to conclude that there are a number of statistical categories where strong performance typically correlates with strong Brownlow medal performance. 

Contested Possessions, disposals and clearances appeared to have the strongest positive correlation with Brownlow medal success, and whilst the strength of this correlation does vary year on year, the positive association is consistent throughout. Since 2012, the player with the most Brownlow votes has finished in the top 10 players in two of the aforementioned statistics. Year on year there is consistent overlap between the top 10 groupings in these 3 statistics.



When looking at the uncontested possession and inside 50 statistics, whilst there is some positive correlation with Brownlow votes, the correlation is not as consistently strong year on year as the 3 statistics mentioned previously. The overlap between the top 10 groupings is limited.

It’s clear from the views created for tackles, goals, and goal assists that they have little to no influence on getting Brownlow Medal votes. Whilst there is the odd outlier some years, these statistics are typically characterised by a lack of positive correlation with success in the Brownlow medal. The cross-over between the top 10 groupings is negligible, or in some cases, non-existent. 

Year on year, the best performers in the Rebound 50s statistic performed poorly in the Brownlow medal. It appeared as though this statistic has a negative correlation with the Brownlow Medal, and many of the top 10 players in the Brownlow did not appear in the top 150 of the Rebound 50 statistic year on year.

Lastly, team success was found to be another important contributing factor in whether a player has success in the Brownlow medal. In every year since 2012, the median points differential of players who received Brownlow votes is higher than the mean, indicating that more votes are going to players with a higher points differential than not. This is also reinforced each year by the ‘player wins’ chart, with two thirds or more of the available votes typically going to players who have played in 10 or more wins.

From this, one can conclude that player performance in certain statistics such as contested possessions, clearances and disposals along with playing in a successful team gives a player a much higher chance of performing well in the Brownlow medal. Likewise, strong performance in statistics such as rebound 50s, tackles or goal assists or playing in a poorly performing team does not lead to success in the Brownlow medal.

FURTHER ANALYSIS

I intend to analyse further the individual games where players have received or not received votes and identify any specific trends that may have lead to the votes being awarded or not. For example, a player may have outperformed their AVG contested possessions in a game where they received Brownlow votes, or missed out on votes performing well in a game where their team lost by a significant margin.

I also am planning to explore further the rebound 50 statistic, to get a greater understanding of why it appears to have a negative correlation with Brownlow medal votes. For example, investigating who the players are that are performing well in this statistic, whether they are playing in losing teams and their performance in other statistical categories that correlate positively with Brownlow votes.

