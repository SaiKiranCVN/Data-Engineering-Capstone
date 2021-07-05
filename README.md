# Data-Engineering-Capstone

## Data Model 

![alt txt](/models.jpg)


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


Dimension Tables - df_immigration, df_demographics

df_temperature:- 
* i94port = code of destination city (mapped from cleaned up immigration data)
* AverageTemperature = average temperature
* City = city name
* Country = country name
* Latitude= latitude
* Longitude = longitude


Dimension Table - I94 immigration data Events Columns:

* i94yr = 4 digit year
* i94mon = numeric month
* i94cit = 3 digit code of origin city
* i94port = 3 character code of destination USA city
* arrdate = arrival date in the USA
* i94mode = 1 digit travel code
* depdate = departure date from the USA
* i94visa = reason for immigration

### Justification and Tech Stack

This data model works, since we can store these 3 tables(star model) in redshift if we wanted, and perform joins to extract all the required information to check if the average temperature effects immigration.
This project uses S3 as storage of raw(extracted) and processed in spark(AWS EMR). Spark is used since, we have more rows(million), and spark uses parallel processing. 

Follow the instructions in the notebook for stepwise implementation!

## Scenarios

The data was increased by 100x.
*  Use Amazon Redshift, since its optimised for aggregation and read-heavy workloads
*  Increase EMR cluster size to handle bigger volume of data

The data populates a dashboard that must be updated on a daily basis by 7am every day.
*  Use AIrflow to schedule dialy, with emails on failure
*  ALso, use DAG Quality checks for every load.

The database needed to be accessed by 100+ people.
*  Can use Redshift, since it supports concurrency upto 50 people, and we can use more than one cluster.
