# sqllachemy-challenge
In this challenge which is module 10 of University of Totonto Data Analyst Bootcamp course.
I was given weather climate data of hawaii in two excel files, one consists of "station,date,prcp and tobs" and the other consists of "station,name,latitude,longitude and elevation"
I have divided this assignment into 2 parts first is climate_starter.ipynb in whichc all the analysis is being done, the other one is app.py in which I have developed a Flask API based on the analysis I have done.
To start the Analysis following dependencies were imported:
%matplotlib inline
from matplotlib import style
style.use('fivethirtyeight')
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd
import datetime as dt
from datetime import datetime, timedelta
import matplotlib.dates as mdates
import sqlalchemy
from sqlalchemy.ext.automap import automap_base
from sqlalchemy.orm import Session
from sqlalchemy import create_engine, func
I have used SQLALchemy create_engine() to connect to the SQLite database.
Used automap_base() function to reflect tables into classes and then stored it into two variable Station and Measurement.
Created a link between Python and Database using Session(engine) function.
Percipitation Analysis and Station Analysis were done.
Percipitation Analysis includes
Finding the most recent date in the dataset.
Using that date, get the previous 12 months of precipitation data by querying the previous 12 months of data.
Selecting only the "date" and "prcp" values and putting them into a variable called results.
Converting results into a pandas dataframe.
Plotting the results and creating a chart.
Providing the summary statistics
Station Analysis includes:
Falculating the total number of stations in the dataset.
Finding the most active stations.
Designing a query that calculates the lowest, highest, and average temperatures that filters on the most-active station id.
plotted the result in histogram.

Part 2: Design Your Climate App
Now that you’ve completed your initial analysis, you’ll design a Flask API based on the queries that you just developed. To do so, use Flask to create your routes as follows:

/

Start at the homepage.

List all the available routes.

/api/v1.0/precipitation

Convert the query results from your precipitation analysis (i.e. retrieve only the last 12 months of data) to a dictionary using date as the key and prcp as the value.

Return the JSON representation of your dictionary.

/api/v1.0/stations

Return a JSON list of stations from the dataset.
/api/v1.0/tobs

Query the dates and temperature observations of the most-active station for the previous year of data.

Return a JSON list of temperature observations for the previous year.

/api/v1.0/<start> and /api/v1.0/<start>/<end>

Return a JSON list of the minimum temperature, the average temperature, and the maximum temperature for a specified start or start-end range.

For a specified start, calculate TMIN, TAVG, and TMAX for all the dates greater than or equal to the start date.

For a specified start date and end date, calculate TMIN, TAVG, and TMAX for the dates from the start date to the end date, inclusive.


