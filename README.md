# Data Visualization Project - Ford Go Bike

Ford GoBike is one of the many Bay Area's bike share system, with thousands of public bikes for use across San Francisco, East Bay and San Jose. These cities are employment hubs and attract thousands of eomployees everyday. Apart from regular weekday commuters, these places have number of tourist attractions which bring stream of visitors from neighboring cities. Like any other big cities, driving during commuter hours is a major problem. Along-with that parking in cities San Francisco can be cost prohibitive. Cities like San Francisco which is a financial and technological hub of West Coast is well connected to South and East Bay via public transit systems like BART and CalTrain.

Not all offices are located near the public transport end points. That used to discourage use of public transport. Companies like Ford Go Bike address the need to short distance travel by providing cheap and offordable bike rental. The company has several plans.

* Single ride for one way trips
* Daily pass for unlimited 30 minute ride 
* Monthly membership which includes first 45 minutes free for every ride

This data set generated enough curiosity in me as I travel to San Francisco for my job and have seen people using rental bikes for traveling short distance. I was eager to get insight to such a business to understand the business model as well get take a look at the fastet growing user segments.

Few questions that popped up in my mind which I thought will guide me during exploratory analysis are:

* Is shared mode of transportation like bike rental getting popolar in a city like San Francisco?
* What is the rate of growth of such type of business?
* What metric values can be used to measure the success of the business?
* What is the user demographics of the bikers?
* Since bike rental companies like Ford offer several plans, which one is growing faster?
* Is there any seasonality associated with the business?

### Exploratory Analysis

As with any data analysis project my exploratory analysis started with understanding the structure of data after I have programatically downloaded bike usage data and loaded it into Panda dataframe. The data had some cleanliness issues. These were:

* Inconsistent data types - for example, timestamp field appearing as string, presence of null values
* Presence of outliers - for example, fields like `age` had values > 100 years for some of the bike users
* Incorrect value in computed field - for example, a handle of records had incorrect value in `ride duration` field which can be computed from `trip end timestamp` and `trip start timestamp`
* Absence of value - Fields like `birth_year` had null values for a small percent of records. They had to deleted as I was interested in break down user dimension by gender and age bracket.

Other than data cleasing I added few derived fiedls to the data frame for ease of subsequent analysis.

#### High level metrics

* Data is for the time period June, 2017 till March, 2019.
* 74% of the bike rental was done by men while 24% was done by women
* On the average female bike renters are little younger than their male counterparts. Median age for female renters is 32 years while for men, it is 33 years
* Total number of bike rentals 2.42 million
* Total distance travelled in 2.5 million miles
* Total duration of bike ride is 536370 hours
* Average distance per ride is little more than 1 mile indicating trips are mostly in local area
* Average distance traveled per hour is 4.66 miles


### Prerequisites

<ol>
<li>Python 3.x</li>
<li>Jupyter Notebook</li>
<li>Pandas</li>
<li>Numpy</li>
<li>MatPlotLib</li>
<li>GeoPy</li>
</ol>

### Content

* `Ford Go Bike Analysis.ipynb`: Jupyter notebook containing data gathering, cleanup and exploratory analysis
* `data/SF_Weather.csv`: Comma delimited San Francisco daily precipitation data obtained from NOAA

### References

* [Python for data analysis](https://www.amazon.com/Python-Data-Analysis-Wrangling-IPython/dp/1491957662/ref=sr_1_3?keywords=Python+for+Data+Analysis%2C+2nd+Edition&qid=1555068716&s=gateway&sr=8-3)
* [Ford Go Bike](https://www.fordgobike.com/)
* [GeoPy](https://geopy.readthedocs.io/en/stable/)
* [MatplotLib User's Guide](https://matplotlib.org/users/index.html)
* [Seaborn category plot](https://seaborn.pydata.org/generated/seaborn.catplot.html)
* [Seaborn multi-plot grid tutorial](https://seaborn.pydata.org/tutorial/axis_grids.html)

## Authors

* **Abhijit Bhattacharya** 

