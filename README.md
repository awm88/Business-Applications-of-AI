# Business-Applications-of-AI

Assignment 1: File 'MMAI5040_–_W21_–Group3_–_Assignment1.ipynb'
Q1. [20 points] The Breakfast Cereal data (cereals.csv) contains nutritional information and
consumer rating of 77 breakfast cereals. The consumer rating is a rating of cereal “healthiness”
for consumer information (not a rating by consumers). For each cereal, the data include 13
numerical variables, and we are interested in exploring this data set. For each cereal, the
information is based on a bowl of cereal rather than a serving size, because most people simply
fill a cereal bowl (resulting in constant volume, not weight). Description of the different
variables appear in the Table 1 below. Explore and summarize the data as follows:
a. Which variables are quantitative/numerical? Which are ordinal? Which are nominal?
b. Compute the mean, median, min, max, and standard deviation for each of the quantitative
variables.
c. Plot a histogram for each of the quantitative variables. Based on the histograms and
summary statistics, answer the following questions:
i. Which variables have the largest variability?
ii. Which variables seem skewed?
iii. Are there any values that seem extreme?

d. Plot a side-by-side boxplot comparing the calories in hot vs. cold cereals. What does this
plot show us?
e. Plot a side-by-side boxplot of consumer rating as a function of the shelf height. If we
were to predict consumer rating from shelf height, does it appear that we need to keep all
three categories of shelf height?
f. Compute the correlation table for the quantitative variables (method corr()). In addition,
generate a matrix plot for these variables.

Q2. [15 points] A machine learning algorithm has been applied to a transaction dataset and has
classified 88 records as fraudulent (30 correctly so) and 952 as non-fraudulent (920 correctly so).
a. Construct the confusion matrix and calculate the overall error rate.
b. Suppose that this routine has an adjustable cutoff (threshold) mechanism by which you
can alter the proportion of records classified as fraudulent. Describe how moving the
cutoff up or down would affect
i. the classification error rate for records that are truly fraudulent
ii. the classification error rate for records that are truly nonfraudulent
c. Below is the decile lift chart for the model applied to new data.

i. Interpret the meaning of the first and second bars from the left.
ii. Explain how you might use this information in practice.
mfr Manufacturer of cereal (American Home Food Products, General Mills, Kellogg, etc)
type Cold or hot
calories Calories per serving
protein Grams of protein
fat Grams of fat
sodium Milligrams of sodium
fiber Grams of dietary fiber
carbo Grams of complex carbohydrates
sugars Grams of sugars
potass Milligrams of potassium
vitamins Vitamins and minerals: 0, 25, or 100, indicating the typical percentage of FDA recommended
shelf Display shelf (1, 2, or 3, counting from the floor)
weight Weight in ouces of one serving
cups Number of cups in one serving
rating Rating of the cereal calcuated by consumer reports

Table 1. Description of variables in the Breakfast Cereal dataset

Variable Description

iii. Another analyst comments that you could improve the accuracy of the model by
classifying everything as nonfraudulent. If you do that, what is the error rate?
iv. Comment on the usefulness, in this situation, of these two metrics of model
performance (error rate and lift).

Q3. [ 25 points] Predicting Airfare on New Routes
The following problem takes place in the United States in the late 1990s, when many major US
cities were facing issues with airport congestion, partly as a result of the 1978 deregulation of
airlines. Both fares and routes were freed from regulation, and low-fare carriers such as
Southwest (SW) began competing on existing routes and starting nonstop service on routes that
previously lacked it. Building completely new airports is generally not feasible, but sometimes
decommissioned military bases or smaller municipal airports can be reconfigured as regional or
larger commercial airports. There are numerous players and interests involved in the issue
(airlines, city, state and federal authorities, civic groups, the military, airport operators), and an
aviation consulting firm is seeking advisory contracts with these players. The firm needs
predictive models to support its consulting service. One thing the firm might want to be able to
predict is fares, in the event a new airport is brought into service. The firm starts with the
Airfares.csv dataset, which contains real data that were collected between Q3—1996 and Q2—
1997. The variables in these data are listed in Table 2 and are believed to be important in
predicting FARE. One question that will be of interest in the analysis is the effect that the
presence or absence of Southwest has on FARE.
a. Explore the numerical predictors and response (FARE) by creating a correlation table and
examining some scatterplots between FARE and those predictors. What seems to be the
best single predictor of FARE?
b. Explore the categorical predictors (excluding the first four) by computing the percentage
of flights in each category. Create a pivot table with the average fare in each category.
Which categorical predictor seems best for predicting FARE?
c. Find a model for predicting the average fare on a new route:
i. Convert categorical variables (e.g., SW) into dummy variables. Then, partition the
data into training and validation sets. The model will be fit to the training data and
evaluated on the validation set.
ii. Use stepwise regression to reduce the number of predictors. You can ignore the
first four predictors (S_CODE, S_CITY, E_CODE, E_CITY). Report the
estimated model selected.
iii. Repeat (ii) using exhaustive search instead of stepwise regression. Compare the
resulting best model to the one you obtained in (ii) in terms of the predictors that
are in the model.
iv. Compare the predictive accuracy of both models (ii) and (iii) using measures such
as RMSE and average error and lift charts.
v. Using model (iii), predict the average fare on a route with the following
characteristics: COUPON = 1.202, NEW = 3, VACATION = No, SW = No, HI =
4442.141, S_INCOME = 28,760, E_INCOME = 27,664, S_POP = 4,557,004,

E_POP = 3,195,503, SLOT = Free, GATE = Free, PAX = 12,782, DISTANCE =
1976 miles.
vi. Predict the reduction in average fare on the route in (v) if Southwest decides to
cover this route [using model (iii)].
vii. In reality, which of the factors will not be available for predicting the average fare
from a new airport (i.e., before flights start operating on those routes)? Which
ones can be estimated? How?
viii. Select a model that includes only factors that are available before flights begin to
operate on the new route. Use an exhaustive search to find such a model.
ix. Use the model in (viii) to predict the average fare on a route with characteristics
COUPON = 1.202, NEW = 3, VACATION = No, SW = No, HI = 4442.141,
S_INCOME = 28,760, E_INCOME = 27,664, S_ POP = 4,557,004, E_POP =
3,195,503, SLOT = Free, GATE = Free, PAX = 12782, DISTANCE = 1976
miles.
x. Compare the predictive accuracy of this model with model (iii). Is this model
good enough or should it be reevaluated once flights begin on the new route?


Assignment 2: File: '5040Assignment2 (1).ipynb'
Q1. [ 15 points] Identifying Course Combinations and Recommending Courses
The Institute of Statistical Education at Statistics.com offers online courses in statistics and
analytics and is seeking information that will help in packaging and sequencing courses.
Consider the data in the file Courstopics.csv. These data are for purchases of online statistics
courses at Statistics.com. Each row represents the courses attended by a single customer.
a. The firm wishes to assess alternative sequencings and bundling of courses. Use
association rules to analyze these data and interpret several of the resulting rules (i.e. as
many as make sense to you).
b. The firm now wants to provide a course recommendation to a student who purchased the
Regression and Forecast courses. Apply user-based collaborative filtering to the data. All
recommendations will be 1. Explain why this happens.

Q2. [ 15 points] Pharmacy Industry
An equities analyst is studying the pharmaceutical industry and would like your help in exploring
and understanding the financial data collected by her firm. Her main objective is to understand
the structure of the pharmaceutical industry using some basic financial measures. Financial data
gathered on 21 firms in the industry are available in the file Pharmaceuticals.csv. For each firm,
the following variables are recorded:
1. Market capitalization (in billions of dollars)
2. Beta
3. Price/earnings ratio

4. Return on equity
5. Return on assets
6. Asset turnover
7. Leverage
8. Estimated revenue growth
9. Net profit margin
10. Median recommendation (across major brokers)
11. Location of firm’s headquarters
12. Stock exchange on which the firm is listed
Use cluster analysis to explore and analyze the given dataset as follows:
a. Use only the numerical variables (1 – 9) to cluster the 21 firms. Justify the various
choices made in conducting the cluster analysis, such as weights for different variables,
the specific clustering algorithm(s) used, the number of clusters formed, and so on.
b. Interpret the clusters with respect to the numerical variables used in forming the clusters.
c. Is there a pattern in the clusters with respect to the categorical variables (10 – 12)? (i.e.
those not used in forming the clusters).
d. Provide an appropriate name for each cluster using any of or all the variables in the
dataset.

Q3. [ 15 points] Customer Rating of Breakfast Cereals
The dataset Cereals.csv, which you saw in Assignment 1, includes information, store display,
and consumer ratings for 77 breakfast cereals. Preprocess the data by removing all cereals with
missing values and answer the following questions.
a. Apply hierarchical clustering to the data using Euclidean distance to the normalized
measurements. Compare the dendrograms from single linkage and complete linkage and
look at cluster centroids. Comment on the structure of the clusters and their stability.
(Hint: To obtain cluster centroids for hierarchical clustering, computer the average values
of each cluster members, using groupby( ) with the cluster centers followed by mean:
dataframe.groupby(clusterlabel).mean().)
b. Which method leads to the most meaningful clusters?
c. Choose one of the methods. How many clusters would you use? What distance is used for
this cutoff? (Look at the dendrogram.)
d. The elementary public schools would like to choose a set of cereals to include in their
daily cafeterias. Every day a different cereal is offered, but all cereals should support a
healthy diet. For thie goal, find a cluster of “healthy cereals”. Should the data be
normalized? If not, how should they be used in the cluster analysis?

Q4. [ 15 points] Car Sales
Consider the data on used cars (ToyotaCorolla.csv) with 1436 records and details on 38
attributes, including Price, Age, KM, HP, and other specifications. The goal is to predict the
price of used Toyota Corolla based on its specifications.
Fit a neural network model to the data. Use a single hidden layer with two nodes.
a. Use predictors Age_08_04, KM, Fuel_Type, HP, Automatic, Doors, Qarterly_Tax,
Mfr_Guarantee, Guarantee_Period, Airco, Automatic_airco, CD_Player,
Powered_Windows, Sport_Model, and Tow_Bar.
b. Use the scikit-learn transformer MinMaxScaler() to scale the data to the range [0,1]. Use
separate transformers for the input and output data. To create the dummy variables, use
the pandas function pd.get_dummies().
c. Record the RMS error for the training data and the validation data.
d. Repeat the process, changing the number of hidden layers and nodes to {single layer with
five nodes}, {two layers, five nodes in each layer}.
i. What happens to the RMS error for the training data as the number of layers and
node increase?
ii. What happens to the RMS error of the validation data?
iii. Comment on the appropriate number of layers and nodes for this application.

Assignment 3: File: Group Reports and Python 1 and 2 
The team project for the course consists of using business analytics / machine learning
techniques to develop an AI solution with new or existing data from a real-world organization.
