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

