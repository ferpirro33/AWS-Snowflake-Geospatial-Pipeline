# Project: Geospatial Data Pipeline (AWS & Snowflake)

## Business Context
This project was developed as a final examination for the Next-Generation Databases module of the Master’s in Big Data Analytics at Universidad Europea de Valencia. It demonstrates a high-scale cloud architecture designed to handle both structured and semi-structured geospatial data for urban analytics.

The architecture demonstrates a hybrid cloud workflow, handling data extraction, SQL-based analytics in Athena, and advanced geospatial processing within Snowflake.

## 🎯 Research Objectives
The analysis processes diverse data formats to provide a 360-degree view of city listings:

CSV Files (Valencia & Madrid): Structured geolocation data, including IDs, coordinates, and market pricing.

GeoJSON Polygons: Semi-structured files defining specific urban perimeters and administrative boundaries.

## 📊 Datasets Overview
The complete development logic is documented in the Jupyter Notebook: pipeline_GeoJSON_AWS_Snow.ipynb.

Data Sources
The pipeline processes the following datasets (included in requiredfiles.zip):

Valencia_data.csv & Madrid_data.csv: Global city geolocation and pricing data.

Valencia_geojson.json & Madrid_geojson.json: GeoJSON polygons defining specific urban boundaries.

## 🛠️ Analytical Roadmap
Data Engineering & Preparation: Initial ETL using Python to filter core features and optimize CSV structures for cloud ingestion.

Serverless Querying: Utilizing AWS Athena to perform cross-city joins and identify pricing trends directly on S3.

Warehouse Architecture: Designing Snowflake ingestion paths and utilizing the VARIANT data type for semi-structured GeoJSON handling.

Task Automation: Implementing Snowflake Tasks and Transient Tables to automate the extraction of the top 90% most expensive listings.

Geospatial Processing: Merging Python’s computational power with Snowflake to execute spatial filtering and distance calculations.

Reverse ETL: Closing the loop by exporting processed insights from Snowflake back to AWS S3 for downstream consumption.

## 💡 Business Impact & Recommendations
The project provides a scalable template for any business requiring location-based intelligence. By automating the filtering of listings within specific geographic zones and calculating proximity to points of interest, the pipeline enables real estate and hospitality firms to make data-driven decisions on asset valuation and market expansion.
