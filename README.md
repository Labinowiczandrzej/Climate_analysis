# Climate_analysis
# Surfs Up

## Projec Summary and Background
W. Avy likes your analysis, but he wants more information about temperature trends before opening the surf shop. Specifically, he wants temperature data for the months of June and December in Oahu, in order to determine if the surf and ice cream shop business is sustainable year-round.

## What You're Creating

> This new assignment consists of two technical analysis deliverables and a written report. You will submit the following:

1. ***Deliverable 1***: Determine the Summary Statistics for June
2. ***Deliverable 2***: Determine the Summary Statistics for December
3. ***Deliverable 3***: A written report for the statistical analysis [`README.md`](https://github.com/Labinowiczandrzej/Climate_analysis). 

## Resources and Before Start Notes:

* Data Source: `SurfsUp_Challenge_starter_code.ipynb` named later as `SurfsUp_Challenge.ipynb`
* Data File: `hawaii.sqlite`
* Software: Matplotli 3.2.2, Python 3.9, Visual Studio Code 1.50.0, Anaconda 4.8.5, Jupyter Notebook 6.1.4, Pandas, Numpy, Sqlalchemy.






## Deliverable 1:  Determine the Summary Statistics for June
Using Python, Pandas functions and methods, and SQLAlchemy, you’ll filter the date column of the Measurements table in the `hawaii.sqlite` database to retrieve all the temperatures for the month of June. You’ll then convert those temperatures to a list, create a DataFrame from the list, and generate the summary statistics.

### Deliverable Requirements:
You will earn a perfect score for Deliverable 1 by completing all requirements below:

1. A working query is written to retrieve the June temperatures from the `date` column of the `Measurement` table.
2. The temperatures are added to a list.
3. ​The list of temperatures is converted to a Pandas DataFrame.
4. Summary statistics are generated for the DataFrame.

 
### Results with detail analysis:

1. **A working query is written to retrieve the June temperatures from the `date` column of the `Measurement` table.**

> Image with `Jupyter Notebook` & `Python` Code below.

**Code and Image**




![name-of-you-image](https://github.com/emmanuelmartinezs/surfs_up/blob/main/Resources/Images/1.1.PNG?raw=true)


2. **The temperatures are added to a list.**

> Image with `Jupyter Notebook` & `Python` Code below.

**Code and Image**


````Python
#  3. Convert the June temperatures to a list.
results = session.query(Measurement.date, Measurement.tobs).filter(extract('month',Measurement.date)==6).all()
````

![name-of-you-image](https://github.com/emmanuelmartinezs/surfs_up/blob/main/Resources/Images/1.2.PNG?raw=true)


3. **​The list of temperatures is converted to a Pandas DataFrame.**

> Image with `Jupyter Notebook` & `Python` Code below.

**Code and Image**


````Python
# 4. Create a DataFrame from the list of temperatures for the month of June. 
df = pd.DataFrame(results, columns=['date','temperature'])
df.set_index(df['date'], inplace=True)
````

![name-of-you-image](https://github.com/emmanuelmartinezs/surfs_up/blob/main/Resources/Images/1.3.PNG?raw=true)


4. **​Summary statistics are generated for the DataFrame.**

> Image with `Jupyter Notebook` & `Python` Code below.

**Code and Image**


````Python
# 5. Calculate and print out the summary statistics for the June temperature DataFrame.
df.describe()
````

![name-of-you-image](https://github.com/emmanuelmartinezs/surfs_up/blob/main/Resources/Images/1.4.PNG?raw=true)


### Deliverable 2: Determine the Summary Statistics for December.
Using Python, Pandas functions and methods, and SQLAlchemy, you’ll filter the date column of the Measurements table in the `hawaii.sqlite` database to retrieve all the temperatures for the month of December. You’ll then convert those temperatures to a list, create a DataFrame from the list, and generate the summary statistics.

### Deliverable Requirements:
You will earn a perfect score for Deliverable 2 by completing all requirements below:

1. A working query is written to retrieve the December temperatures from the `date` column of the `Measurement` table.
2. The temperatures are added to a list.
3. ​The list of temperatures is converted to a Pandas DataFrame.
4. Summary statistics are generated for the DataFrame

### Results with detail analysis:

1. **A working query is written to retrieve the December temperatures from the `date` column of the `Measurement` table.**

> Image with `Jupyter Notebook` & `Python` Code below.

**Code and Image**


````Python
# 6. Write a query that filters the Measurement table to retrieve the temperatures for the month of December.
session.query(Measurement.date, Measurement.tobs).filter(extract('month',Measurement.date)==12).all()
````

![name-of-you-image](https://github.com/emmanuelmartinezs/surfs_up/blob/main/Resources/Images/2.1.PNG?raw=true)


2. **The temperatures are added to a list.**

> Image with `Jupyter Notebook` & `Python` Code below.

**Code and Image**


````Python
# 7. Convert the December temperatures to a list.
results = session.query(Measurement.date, Measurement.tobs).filter(extract('month',Measurement.date)==12).all()
````

![name-of-you-image](https://github.com/emmanuelmartinezs/surfs_up/blob/main/Resources/Images/2.2.PNG?raw=true)


3. **​The list of temperatures is converted to a Pandas DataFrame.**

> Image with `Jupyter Notebook` & `Python` Code below.

**Code and Image**


````Python
# 8. Create a DataFrame from the list of temperatures for the month of December. 
df = pd.DataFrame(results, columns=['date','temperature'])
df.set_index(df['date'], inplace=True)
````

![name-of-you-image](https://github.com/emmanuelmartinezs/surfs_up/blob/main/Resources/Images/2.3.PNG?raw=true)


4. **​Summary statistics are generated for the DataFrame.**

> Image with `Jupyter Notebook` & `Python` Code below.

**Code and Image**


````Python
# 9. Calculate and print out the summary statistics for the Decemeber temperature DataFrame.
df.describe()
````

![name-of-you-image](https://github.com/emmanuelmartinezs/surfs_up/blob/main/Resources/Images/2.4.PNG?raw=true)



## Deliverable 3: A written report for the statistical analysis
For this part of the Challenge, write a report that describes the key differences in weather between June and December and two recommendations for further analysis.

### The analysis should contain the following:

1. **Overview of the analysis:** Using Python, Pandas functions and methods, and SQLAlchemy, we’ll filter the date column of the Measurements table in the `hawaii.sqlite` database to retrieve all the temperatures for the month of June. We'll then convert those temperatures to a list, create a DataFrame from the list, and generate the summary statistics. Once our dataframe is created we are able to get our summary statistics by using the `df.describe()` code and method. 
> Below our Analysis that what we found:

2. **Results:** Data Provided gave us a visibility that on months of June and December, our location had a total Temps of:

**June Temps - Analysis and Result**
* Count of 1700 
* Mean of 74.94 
* Std of 3.26 
* Min of 64.00 
* 25% of 73.00 
* 50% of 75.00
* 75% of 77.00
* Max of 85.00


**June Temps - Report**
> Image with `Jupyter Notebook` & `Python` Code below.

![name-of-you-image](https://github.com/emmanuelmartinezs/surfs_up/blob/main/Resources/Images/1.4.PNG?raw=true)



**December Temps - Analysis and Result**
* Count of 1517 
* Mean of 71.04 
* Std of 3.75
* Min of 56.00 
* 25% of 69.00 
* 50% of 71.00
* 75% of 74.00
* Max of 83.00


**December Temps - Report**
> Image with `Jupyter Notebook` & `Python` Code below.

![name-of-you-image](https://github.com/emmanuelmartinezs/surfs_up/blob/main/Resources/Images/2.4.PNG?raw=true)


3. **Summary:** Based on our Data Analysis, Data Provided, we can state as a high-level summary of results that Standard deviation is 3.25 in June and 3.75 in December, making a 0.5 difference between both seasons.
 
    In addition, current data provide attributes such precipitation and others, with two queries that our analysis pursue, performing weather data for June and December that helps results to decide how we would like to build the shop and what areas would make this location attractive to visitors to stop by and have a successful business.
