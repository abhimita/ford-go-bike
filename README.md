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

### Structure of dataframe

It is useful to understand the meaning of each of the fields in the dataframe schema. Description of each of the fields are picked up from __[here](https://www.fordgobike.com/system-data)__

**duration_sec** - Trip Duration (seconds)<br>
**start_time** - Start Time and Date<br>
**end_time** - End Time and Date<br>
**start_station_id** - Start Station ID<br>
**start_station_name** - Start Station Name<br>
**start_station_latitude** - Start Station Latitude<br>
**start_station_longitude** - Start Station Longitude<br>
**end_station_id** - End Station ID<br>
**end_station_name** - End Station Name<br>
**end_station_latitude** - End Station Latitude<br>
**end_station_longitude** - End Station Longitude<br>
**bike_id** - Bike ID<br>
**user_type** - User Type (Allowable values atr - subscriber or customer. “Subscriber” means member. “Customer” means people who are not members but are causal users<br> 
**member_birth_year** - Member Year of Birth<br>
**gender** - Member Gender<br>
**bike_share_for_all_trip** - which tracks members who are enrolled in the Bike Share for All program for low-income residents

#### High level metrics

* Data is for the time period June, 2017 till March, 2019.
* Total number of bike rentals 2.42 million
* Total distance travelled in 2.5 million miles
* Total duration of bike ride is 536370 hours
* Average distance per ride is little more than 1 mile indicating trips are mostly in local area
* Average distance traveled per hour is 4.66 miles

### Segmentation of bikers

Data has attributes of bikers - gender, age & user type. I would like to segment the bikers by these attributes to highlight any usage pattern differences that I discover.

* 74% of the rentals belong to male bikers while 24% belong to females
* On an average female bikers tend to be tad youndger than that of male bikers. Median age of female bikers is 32 while it is 33 for male counterparts.
* Age analysis segmented by user type (members & non-members from now on referred as subscribers & customers respectively) brings out another noticable pattern - customers tend to be younger on the average compared to subscribers. Data shows that it holds good for female & male genders.

| Member Gender | User Type     | Median Age  |
| ------------- |:-------------:| -----------:|
| Female        | Customer      | 30          |
| Female        | Subscriber    | 32          |
| Male          | Customer      | 31          |
| Male          | Subscriber    | 33          |

* Another difference that was evident from metric values (rental count, average miles traveled and average ride duration), usage pattern is quite different from subscribers vs customers. On the average customers tend to travel higher distance as well as for longer duration.


| Gender | Type       |  Age   | Count  | Mean Duration (min)| Median Duration (min)| Mean Distance (mile)| Median Distance (mile) |
| -------| ---------- | ------ | ------ | ------------- | ------------- | -------------- |----------------|
| Female | Customer   | 30     |   86666| 16            | 30            | 0.98           | 1.09            |
| Male   | Customer   | 31     |  186572| 13            | 25            | 0.98           | 1.10            |
| Female | Subscriber | 32     |  522545|  9            | 12            | 0.88           | 1.04            |
| Male   | Subscriber | 33     | 1660569|  8            | 10            | 0.84           | 0.97            |


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

