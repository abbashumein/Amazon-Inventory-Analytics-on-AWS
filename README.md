# Amazon-Inventory-Analytics-on-AWS
This project demonstrates a complete data analytics pipeline built on Amazon Web Services (AWS) using free-tier services. The objective was to solve a specific business problem for a warehouse manager: an "inventory crisis" where they needed to identify slow-moving and fast-moving products to optimize storage space and prepare for the holiday season.

The project showcases my ability to:

Ingest and store data in a data lake.

Perform schema discovery and catalog data for querying.

Analyze data using standard SQL queries.

Provide actionable, data-driven recommendations.

The Problem: Inventory Crisis
The warehouse manager is facing a two-fold problem:

Storage Overload: The warehouse is running out of space, and a strategy is needed to identify which products to discontinue or put on clearance.

Holiday Season Preparation: They need to know which products are popular and should be stocked up for the upcoming holiday season.

Solution Architecture

The project leverages the following AWS services:

Amazon S3 (Simple Storage Service): Used as a data lake to store the raw "Amazon Sale Report" dataset in a CSV format. This provides a scalable, secure, and durable storage solution.

AWS Glue: A serverless data integration service used to:

Crawl the S3 bucket: The Glue Crawler automatically scans the CSV file in S3, infers the schema, and creates a metadata table in the AWS Glue Data Catalog.

Schema Discovery: The crawler correctly identified all columns and their data types from the source file.

Amazon Athena: An interactive query service that makes it easy to analyze data directly in S3 using standard SQL. Athena uses the metadata from the Glue Data Catalog to query the data without needing to load it anywhere.

The Dataset
The dataset used is the "Amazon Sale Report," a CSV file approximately 70 MB in size. The key columns used for this analysis included:

SKU: Unique identifier for each product.

Qty: The number of units sold.

Status: The status of the order (e.g., 'Shipped').

Date: The date of the sale.

Amount: The sale amount

Analysis and Findings
To solve the inventory crisis, a series of SQL queries were executed in Amazon Athena to analyze the sales data. The queries were designed to identify sales velocity and provide clear, actionable recommendations.

Key Queries Executed
1. Identifying Slow-Moving Inventory (Products for Discontinuation/Clearance)

Recommendation: The top 100 products from this query are highly popular and should be stocked up in preparation for the holiday shopping season.

Project Outcome
The analysis provided direct, data-backed insights to the warehouse manager. The project successfully demonstrates the entire data lifecycle, from raw data to actionable business intelligence, all within a scalable and cost-effective cloud environment.




