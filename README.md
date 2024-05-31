# Tennis_Match
# Summary
The player with more than 50 matches were found by the count of won + lost matches. I
selected Rafael Nadal as a player for all the other parts of this question:
• A new column ‘ result’ was added to the dataFrame to record the status of
Rafael’s matches and was grouped by tourney_name and Surface for
visualisations to see his win/loss record.
• I set criteria for high pressure situations where the match would be high
pressured if it follows these:
o If there is a tie break (based on the 'score' column). Example if the score
in a set was '7-6' or '6-7'
o Based on the 'score', see if the match went to the total amount of sets
defined in 'best of' column. Example for best of 3 matches, the third set is
the deciding set if the previous sets have been won by each player.
o If the player is playing with a higher-ranked opponent.
• Based on the background knowledge for Tennis, the tennis players are under
pressure when they're facing break points so based on this to Further judge
Rafael’s performance, a break points ratio was calculated.


The serving ability was calculated by summing up aces made by the winner and serves
in and won. Based on this, the male and female data were categorised and the
performance of top 10 best servers for each gender was calculated. The Serve ability for
each gender was compared using the surface the matches were played on and the
players age to see if these factors contribute to any change.


In order to predict the aces for a match, I added another column ‘total_aces’ by
summing up the aces of winner and the loser player of each match. To only keep the
features that were highly corelated with the ‘total_aces’, the relevant categorical
columns were converted to integers using one-hot encoding and a correlation
coeWicient of the each integer column with the ‘total_aces’ was calculated. I set a
threshold of 0.5 (positive correlation) which meant columns having correlation values
less than 0.5 were discarded. Two columns having correlation values of -0.5 were
discarded because by manually looking at the data, I did not find them useful in
predicting aces.
Since the data had null values, it was dealt by imputing values using KNN which finds
the distance between points and fills the data by the values in a column, that the closet
(similar) neighbour to that point had, for the same column. The Multiple regression
model was used to calculate the number of aces for each match and the models
performance was evaluated using mean squared error and mean absolute error.
