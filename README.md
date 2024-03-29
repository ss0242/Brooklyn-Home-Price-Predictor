# Brooklyn-Home-Price-Predictor
This is a project implementing the machine learning model for predict home sale prices for Brooklyn using Google Cloud Platform


1)  Research question:  what is the group trying to learn or question to answer? Who is interested (audience)?

 I have a house at brooklyn. Based on the certain parameters such as area(per square ft), zipcode, nieghbourhood, year of built and      type of property I would like to know the estimated sale price of the kind of property I am looking for.
 

2)  Domain and Data: 

Housing(Real Estate)/Finance
Data Source: https://www1.nyc.gov/site/finance/taxes/property-annualized-sales-update.page


Preprocessing:
There is column in sales price which contain zero values. These are property transfers from relatives. They have to ignored while analysing the data


Size of data: 77MB (compressed file); nearly 3.9 Million rows; data from 2007 to 2018

EDA: 1) Bar graph of tax class (what percentage to each tax class)
     2)Boxplots of land_sqft or gross_sqft by tax class (what are the ranges of property square footage for each tax class)
     3)Scatter plot of land_sqft by sales_price (What type of relationship is here?)
     4)Scatter plot of year_built by sales_price (Potential look at value of properties overtime)
     
Dashboard: Price of nieghbourhood from 2007 to 2018 for the User and change in the median price of houses across all nieghbourhoods of brooklyn for data engineers  

GCP further processing/ Evaluation of results: Evaluation of results will be tailored based on the machine learning model. For logistic regression, we will use a confusion matrix and Area Under the Curve (AUC) of Receiver Operating Characteristics (ROC) curve. For linear regression, we will use Root Mean Squared Error (RMSE) and R-squared. 


Steps for production Model: Extract phase will involve polling the datasource https://www1.nyc.gov/site/finance/taxes/property-annualized-sales-update.page every year. This will be a scheduled cron job that will be run periodically. The data is usually made available in the month of april. Upon the extraction of the data which is originally in the xls format, the file is transformed to csv format. The csv file is further transformed to remove unnecessary headers from the file to make  it fit for building machine learning models. 
     
     
Final dashboard for user group will make use of the predictions from our models into appealing visuals to help our target user group make better decisions regarding their real estate transactions.

The dataset can be found at this location: https://drive.google.com/open?id=1r2nISvGxzBH0qE4nMHM05bMFGYhsfF2u

<b>Please refer the notebook Data Exploratory Analysis Brooklyn Houses Prices 2003 - 2018 (v-3).ipynb. which contains the full coverage of the project</b>

<b>Please refer the file MergedBrooklynDashboard - users.pptx and MergedBrooklynDashboard - users.twb in order to see the dashboards. The Dashboard uses the data source kept in JoinedBrooklyn zipped folder</b>

# Abstract #
A couple of papers related to housing price predictions were referred to decide upon the variable.
As per the paper[1],Physical conditions are properties possessed by a house that can be observed by human senses, including the <b>size of the house</b>, the number of bedrooms, the availability of kitchen and garage, the availability of the garden, the area of land and buildings, and the age of the house, while the concept is an idea offered by developers who can attract potential buyers, for example, the concept of a minimalist home, healthy and green environment, and <b>elite environment</b>. The elite environment is captured by the variable named neighborhood.
Furthermore, as per the paper[2],The property attributes available and used for their study were: <b>the
square feet of living area (sqft) </b>, the number of bedrooms (bed#), the number of baths (bath#), the<b> number of years since the property was built (age) </b>.
Lastly, as per the paper[3], the some of the variables taken into consideration are Size, Date Built. Other variable considered include Restraunts, Grocery Stores, Nightlife. There variables have been captured under the larger abmit of neighborhood

# References #
1. Modeling House Price Prediction using Regression Analysis and Particle Swarm Optimization ,International Journal of Advanced Computer Science and Applications (IJACSA), Vol. 8, No. 10, 2017
2. Predicting Housing Value, The Journal of Real Estate Research (JRER)  Vol. 22  No. 3 – 2001 
3. Housing Price Prediction, An Nguyen, Appendix Table 6
<table>
<th>Team member</th>	<th>Duties</th>
 <tr>
<td>Daniel</td> <td>	  DashBoards on Tableau, Data Exploration, Random Forest Model prediction</td>
  </tr>
 <tr>
<td>Jason</td><td>	    Initial DataSet finding, Data Cleansing </td>
</tr>
 <tr>
<td>Harshini</td>  <td>Initial DataSet finding, git-hub site curation</td>
</tr>

<td>Sagar</td> 	   <td>Creating shell scripts for loading the data into the bigquery, Initial visuals regarding data(word cloud/lms plot), Linear regression model (normalised/ unnormalised), Creating the model infrastructure(i.e preparation of project steps)</td>

</table>

