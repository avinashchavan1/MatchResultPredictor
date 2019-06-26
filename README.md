# MatchResultPredictor

## Introduction
The Project is mainly about predicting the results of ipl matches, using the old ipl match histroy. Here we are analysing the old match results, based on that we are judging the outcome of randomly chosen match  and varifying the accuracy of prediction with actual result.
Approach:
1)Normal approach using clustering 
   Here we are creating batsman and bowler clusters using K means algorithm.
2)Decision Tree approach 
		   Here we are Converting the data into decision tree model and using this we are predicting the result 

## Phase 1  
Reference to get ipl data 
1)www.espncricinfo.com/ 
Using this website we scrape the html to get the player list with differnt attributes like runs, balls faced, strike rate, avarage, etc..

Initially  we scrape each individual team data later using this data we merged all and extracted the dataset which we wanted.



Links for each individual team data :  
http://stats.espncricinfo.com/ci/engine/records/averages/batting.html?id=117;team=4343;type=trophy
similarly Change team id  with 4347, 4344, 5845, 4342, 4788, 4341, 4346, 4787, 4345, 5843 to get individual tam data 
We have used BeautifulSoup python libary to scrape the html and extract data 

We loaded the dataset to HDFS to make clusters.  
we are checking the batsman and bowler combination in the original dataset to use it for prediction, but there are some batsman and bowler combination did not occur in the dataset, in order to overcome this we used concept of clusering. Clustering is mainly putting every batsman and bowler in a perticular cluster number between 1 to 10 using K means algorithm. And based on the parametre we are judging which specific cluster the player belongs to, the parametres are strike rate, avarage, runs scored and ball faced for batsman and for bowler we are taking wickets taken, overs bowled, bowling avarage, bowling strike rate and economy.  
For the new players we are assinging the values of cluster for which he belongs to.  

The parameters used for clustering batsman – Runs, Strike Rate, Average, balls faced  
The parameters used for clustering bowlers – Wickets, Economy, Average, Strike Rate, overs bowled, 
