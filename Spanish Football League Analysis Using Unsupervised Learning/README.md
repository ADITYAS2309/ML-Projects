# **Analysis of LaLiga 2023/24 Using Unsupervised Learning**

## **Overview**

In the modern era of sports analytics, understanding player performance and characteristics through data is crucial for gaining competitive advantages. This project applies Principal Component Analysis (PCA) to La Liga players from the 2023/2024 season. PCA is a statistical technique used to reduce the dimensionality of large datasets while preserving as much variance as possible. By doing so, it simplifies the complexity of player data, making it easier to identify patterns and insights.

The primary objectives of this project are:

1. Utilize PCA to reduce the multidimensional player performance dataset into a concise set of principal components, simplifying analysis and interpretation.
2. Compare individual players or groups of players based on their principal components to uncover similarities and differences in playing styles, strengths, and weaknesses.
3. Identify distinct player types based on performance metrics, facilitating a deeper understanding of player roles and contributions within teams.
4. Generate actionable insights into the key factors influencing player performance, which can inform strategic decisions related to player development, recruitment/transfers, and tactical planning.

## **Data**

The data was taken from kaggle. 
Link to the dataset: https://www.kaggle.com/datasets/sdelquin/laliga-data3

## **Python Libraries Used**

* Pandas
* Numpy
* Matplotlib
* Seaborn
* Sklearn

## **Data Cleaning & Pre-processing**

* The dataset consisted of 681 players measured along over 150 characteristics. The data had players teams that were not part of Laliga 2023/24. These were players who played in Laliga for a short time before being transferred to other teams. These players were removed.

* Columns like gender, nickname, player.url and other unnessary columns were dropped.

* DOB was replace by Age. The Age was calculated with reference to the starting data of the season.

* Duplicated players were removed.

* Null values for height and weigth were imputed with there respective means.

* For all other columns which measured different characterirics, a null value meant a measurement of 0. For example, the null under goals_scored column meant the respective player scored 0 goals for the season. Such nulls were replaced with value of 0 over all other columns.

* Selection of players for Analysis: There were players with a small game time. These would be outliers and were removed.Laliga and sport leagues generally have a criteria to filter players for conducting analysis, and using that criteria, we will consider players who have played 900 minutes (equivalent to 10 full matches).
  
* We split the datasets based on the positions of the players. Since players play at different positions, it will be meaningfull to categorize them as per position and then conduct the analysis. This is because each position have distinct roles and skill sets and combining these diverse metrics in a single PCA might obscure patterns specific to each position.
  
* All the columns were standardize to have a mean of 0 and standard deviation of 1

## **Results**

### PCA on Forwards

PCA was carried on the datasets with columns relevant to the forwards. 4 principle components were selected from scree plot which explain 63% of the total variance.

**1st Principle Component: False 9/Wingers vs Traditional Strikers**

The 1st Principle Component acoounts for 31% of the total variation. Majority of loadings are positive, and those few negatives can be classified insignificant. The first component is along the direction of nature of forwards. Players with a positive PC1 score can be classified as False 9/Wingers, who are good at creating goal scoring opportunities, setting up of goals, are pretty much involved in the game, and the attacks run through them. These include A. Griezmann, L. Ocampus, I. Aspas, F. Olivera, etc. Players with negative PC1 scores are more of traditional strikers, who are focused on scoring goals, do not touch the ball quite often, lie around/behind the defenders and are relied on players to feed them balls to score. These inlcude players like R. Yaremchuk, J. Morales, U. Sadiq, I. Romero, etc. Refer the plot to know more about differnt players.

**2nd Principle Component: Prolific vs Cautious Shooters**

The 2nd Principle Component accounts for 18% of total variation.  It describes the shooting abilities of forwards. Forwards with high positive score have taken lot of shots, 


stabl/calm vs unstable defenders
aerial vs ground dominance
ball playing defenders vs defensive liability
goal scorings vs traditional defenders



















