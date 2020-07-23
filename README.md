# ALL-NBA-DNN

Introduction
The All-NBA Team is an end-of-season award given to the best players in the league. These are voted by a panel of sportswriters and broadcasters and are composed of three five-man lineups. These lineups are then distinguished as First Team, Second Team and Third Team composed of two guards, two forwards and one center. Selection is based on a weighted point voting system with five points for a First Team vote, three points for a Second Team vote, and one point for a Third Team vote. The five players with the highest point totals make the first team, with the next five making the second team and so forth.

Data and Method
Our dataset starts with the 1988-89 NBA season and spans the period until the 2018-19 season. The 1988 NBA season is when the NBA started the current format of three separate All-NBA teams. Before the 1988 season, only two All-Nba teams where selected. The raw data consists of all countable stats like points, rebounds, shooting percentages, etc. as well as several of the so-called advanced starts such as win shares, VORP, PER, etc. This information was scraped directly from the basketball reference website.

Machine learning involves computers discovering how they can perform tasks without being explicitly programmed to do so. It involves computers learning from data provided so that they carry out certain tasks, in this case, assign probabilities for individual players to make the All-NBA First, Second or Third Teams, or miss the award completely based on their season stats.

We will construct a Deep Neural Network (DNN) to predict the probabilities each individual player will be the recipient of each of the All-NBA Teams. We will train our supervised learning model using historical data from the seasons from 1988 to 2018 with a series of 18 different stats both counting (per game) and advanced. We performed a grid search of the hyperparameters to optimize the model. This means we tested different combinations for factors that determine how our models fit the data and select the combination that results in the best score. Finally, the model output of the probabilities will be weighted to mirror the real-life All-NBA point system. For example, if our model predicts Player X to have a 0.50 probability to be in First-Team, a probability of 0.30 to be in Second Team and a probability of 0.20 to be in Third Team the total point calculation would be:

Player X = 0.50 x 5 + 0.30 x 3 + 0.20 x 1 = 3.6 Total Points

Noting that probabilities add up to 100%, with this scoring system the maximum score possible is 5.0. The predicted First All-NBA Team is selected from the two highest-scoring guards, two highest-scoring forwards and the highest scoring center. The next five players by position are the Second Team, and the next five are the Third Team.
