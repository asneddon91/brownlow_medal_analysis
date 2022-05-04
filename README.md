# brownlow_medal_analysis
Analysing whether strong performance in individual statistical categories correlated with success in the Brownlow Medal. With this being my first attempt at producing a case study, I'm looking to outline the process I followed as well as the data I uncovered.

The Brownlow Medal is awarded to the AFL player considered the 'best and fairest' player during the home and away season. The medal is voted on collectively by the three on-field umpires, who award votes to whom they consider to be the 3 players on the ground who best fit the voting criteria. The votes are awarded under a 3-2-1 system, i.e. 3 votes, 2 votes and 1 vote are awarded to the players the umpires considered the 'best and fairest', second best and third best in the game respectively.

Using the data provided in the .CSV files above, I set out to identify in which individual statistical categories (i.e. contested possessions, disposals, goals, tackles etc), strong performance by players positively correlated with success in the Brownlow Medal between the years 2012 & 2021.

EXPLORING THE DATA

I decided to begin by reviewing the statistical performance of the Brownlow medalist from each year. Using the below SQL query, I was able to locate the Brownlow Medal winners for each year.

<img width="287" alt="brownlow winners query" src="https://user-images.githubusercontent.com/82799348/166616671-5f76b937-b797-44ec-b7f9-7c221cf48d76.png">

