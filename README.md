# Data Modeling using DBT on Airbnb Data and Snowflake
The goal of this project is to perform various data modeling using DBT capabilities on an Airbnb public dataset which where uploaded on Snowflake data warehouse.


## 1. Project Description
In this project, the aim is to deep dive into the Airbnb renting data to get more insight on different aspect of this industry. For this matter, we use the following Airbnb datasets for Listings, Hosts information, and clients reviews:
- https://dbtlearn.s3.amazonaws.com/hosts.csv
- https://dbtlearn.s3.amazonaws.com/reviews.csv
- https://dbtlearn.s3.amazonaws.com/listings.csv

We use the following functionality from DBT which can be used as the baseline for future data visualizations, analysis, more complex analytics engineerings, etc.:
 * dbt Models
 * dbt Materializations
 * dbt Tests
 * dbt Documentation
 * dbt Sources, Seeds, Snapshots
 * dbt Hooks and Operations
 * Jinja and Macros
 * Analyses, Exposures 
 * dbt Seeds
 * Data Visualization (Preset) --> To be added to the project Repo


## 2. Tech Stack
- DBT-core
- Python
- Preset
- Snowflake
- Dagster (Orchestration tool)

## 3. Modeling:
The graph represents a data workflow using DBT to transform Airbnb data stored in Snowflake. Raw data from Airbnb is uploaded into Snowflake under three categories: hosts, listings, and reviews. The dim_hosts_cleansed and dim_listings_cleansed models clean the host and listing data, respectively. The scd_raw_listings snapshot captures changes in the listing data over time. These cleansed and snapshot data sets are further transformed; dim_listings_with_host combines cleansed listings and hosts data, while mart_fullmoon_reviews integrates review data with full moon dates from seed_full_moon_dates to analyze patterns in reviews. This structured approach ensures data quality and enables sophisticated analysis.

The provided graph represents a data modeling process using DBT (Data Build Tool) with Airbnb data that has been uploaded to the Snowflake data warehouse. Here’s an explanation of the workflow:

1. Sources:

    - <b>hosts</b>: Contains raw host data.
    - <b>listings</b>: Contains raw listing data.
    - <b>reviews</b>: Contains raw review data.

2. Models:

    - <b>dim_hosts_cleansed</b>: Cleansed data model for host information.
    - <b>dim_listings_cleansed</b>: Cleansed data model for listing information.
    - <b>scd_raw_listings</b>: Snapshot of raw listing data for slowly changing dimensions (SCD).
    - <b>fct_reviews</b>: Fact table model for reviews.
    - <b>seed_full_moon_dates</b>: Seed data for full moon dates.

3. Derived Models:

    - <b>dim_listings_with_host</b>: Combines cleansed listings and hosts data.
    - <b>mart_fullmoon_reviews</b>: Combines review data with full moon dates to analyze reviews around full moon dates.

In this setup, DBT is used to clean, transform, and model data from the raw Airbnb dataset stored in Snowflake, enabling more advanced analytics and reporting.

![image](https://github.com/soroushr123/Data_Modeling-AIRBNB-Snowflakes/blob/main/DBT_Diagram.png) 
<p align="center"> Figure: Overall pipeline of DBT Data modeling </p>

## 4. Project File Struture:
1. Refer to Snowflake_setup folder and follow the instruction to setup the dataset
2. Use DBT RUN and DBT TEST after opening terminal in dbt_airbnb_snowflake folder to make the complete dbt profile for the project.
3. Dagster folder can be used to perform data orchestration and scheduled run on the data

### Disclaimer
This project is based on this course project: 
https://www.udemy.com/course/complete-dbt-data-build-tool-bootcamp-zero-to-hero-learn-dbt/
# Data_Modeling-AIRBNB-Snowflakes
