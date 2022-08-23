# Shopmob-ETL

These pipelines extract supermarket sales data from the Imonggo API as per https://help.imonggo.com/en/collections/154448-api, convert it to a format more amenable for analytics, then stores the data in an Azure Blob Storage container. The code (ex installation i.e. pip install ...) can be implemented manually as ipynb script, a local .py executable, or on Azure Functions, Azure Synapse Spark pools, or Databricks (analogous services on other cloud providers can be used as well. I have this code run daily at 8pm (when the store closes) using a time trigger.

Code for extracting invoices/products from Imonggo and storing in Azure Storage as flat file
For each page of invoices/products (50 invoices/products per page):

1)Retrieve the pages of data using Imonggo API as XML

2)Convert XML to JSON

3)Flatten JSON

4)Convert JSON to CSV

5)Upload to Azure Blob Storage container
