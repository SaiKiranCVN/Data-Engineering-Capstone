# Data-Engineering-Capstone

## Data Model 

![alt txt](/model.jpg)


Fact Table - This will contain information from the I94 immigration data joined with the city temperature data on i94port 
Columns: 
* i94yr = year
* i94mon = numeric month
* i94cit = 3 digit code of origin city
* i94port = 3 character code of destination city
* arrdate = arrival date
* i94mode = 1 digit travel code
* depdate = departure date
* i94visa = reason for immigration
* AverageTemperature = average temperature of destination city


Dimension Tables - df_temperature, df_demographics

df_temperature:- 
* i94port = code of destination city (mapped from cleaned up immigration data)
* AverageTemperature = average temperature
* City = city name
* Country = country name
* Latitude= latitude
* Longitude = longitude


df_demographics:- 
* State Code = 2 letter state code
* City = city name
* Male Population
* Female Population
* Total Population
* Foreign-born
* Number of Veterans
* Race
* Count
* Average Household Size

Follow the instructions in the notebook!
