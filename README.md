# Project: End-to-End Geospatial Data Pipeline: AWS & Snowflake Cloud Architecture

## Overview
This project was originally developed as a final examination for the Next-Generation Databases module within the Master in Big Data Analytics at Universidad Europea de Valencia. It has been refined and containerized for full reproducibility within this portfolio.

The architecture demonstrates a hybrid cloud workflow, handling data extraction, SQL-based analytics in Athena, and advanced geospatial processing within Snowflake.

## Setup & Installation
To ensure environment isolation and prevent dependency conflicts, please follow these steps:

Virtual Environment: Create a dedicated Python environment using GitBash.

Dependencies: Install the required libraries by executing:

Bash
pip install -r requirements.txt


## Execution Workflow
The complete development logic is documented in the Jupyter Notebook: pipeline_GeoJSON_AWS_Snow.ipynb.

Data Sources
The pipeline processes the following datasets (included in requiredfiles.zip):

Valencia_data.csv & Madrid_data.csv: Global city geolocation and pricing data.

Valencia_geojson.json & Madrid_geojson.json: GeoJSON polygons defining specific urban boundaries.

## Core Pipeline Activities
ETL & Data Cleaning: * Leveraged Python (Pandas) to parse and filter raw CSV files, extracting key features: id, latitude, longitude, and price.

Serverless Analytics with AWS Athena: * Staged data in S3 and performed SQL analysis using Athena to identify high-value listings (>100 USD) and execute cross-city price correlations via JOIN operations.

Snowflake Data Ingestion: * Architected an automated ingestion path from S3 to Snowflake.

Data Optimization: * Implemented Snowflake Tasks to automate the creation of Transient Tables, applying business logic to isolate the top 90th percentile of high-priced listings.

Semi-Structured Data Handling: * Ingested GeoJSON files into Snowflake using the VARIANT data type, enabling efficient JSON parsing.

Geospatial Analysis: * Integrated Python with Snowflake to perform spatial joins: * Filtering listings strictly located within GeoJSON boundaries. * Calculating Euclidean/Haversine distances from listings to the Valencia city center.

Data Reverse ETL: * Final processed dataframes are written back to Snowflake directly from Python and subsequently exported to S3 for downstream consumption.
