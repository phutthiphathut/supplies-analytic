# supplies-analytic
#Exploring Sales Data and Analysis with MongoDB and Python
In this article, we'll walk through the process of exploring sales data and performing data analysis using MongoDB and Python. We'll cover various steps, from setting up the environment to extracting valuable insights from the data. The goal is to showcase how to work with MongoDB, establish secure connections, and derive meaningful information from sales records.

Step 1: Package Installation
Our journey begins with the installation of essential Python packages. We use the %pip command to install the required packages, which include:

dnspython: A Python library for working with DNS (Domain Name System) data.
pymongo: A Python driver for MongoDB, enabling interaction with MongoDB databases.
certifi: A package that provides a collection of trusted authority certificates for secure network connections.
Step 2: Importing Libraries
With the packages installed, we import the necessary libraries and modules to set up our data analysis environment. Two key imports are made:

from pymongo import MongoClient: We import the MongoClient class from the pymongo library, which allows us to establish connections to a MongoDB server.
import certifi: We import the certifi library, which provides trusted certificates for secure network connections.
Step 3: Database Connection Setup
Now that our environment is prepared, we proceed to set up a connection to a MongoDB database. We use MongoDB Atlas for hosting the database. The connection URL, username, and password are provided to the MongoClient constructor. This step establishes a connection to the database and defines the specific database and collection we want to work with.

Step 4: Showing Top 10 Products by Sales
We kick off the data analysis by finding the top 10 products based on sales. To achieve this, we define an aggregation pipeline:

We start by unwinding the items array, which breaks down sales records into individual product items.
Sales for each product are calculated by multiplying the quantity sold by the price of each item.
The data is then grouped by product name, and the results are sorted in descending order by total sales.
Finally, we limit the output to the top 10 products and present the results in a clear and concise format.
Step 5: Showing Top 3 Products by Sales for Each Store Location
The next step involves identifying the top 3 products by sales for each store location. This is achieved through a comprehensive aggregation pipeline:

We begin by unwinding the items array to access individual product sales records.
Similar to the previous step, we calculate sales for each product item by multiplying quantity and price.
The data is grouped by product name and store location.
The results are further sorted based on total sales.
We group the results by store location and keep only the top 3 products for each location.
The final output presents the store location and the top 3 products by sales for each store.
Step 6: Showing Store Rankings Based on Total Sales
To understand how different store locations perform in terms of total sales, we rank them based on their sales figures. The process involves:

Unwinding the items array to access individual sales records.
Calculating the sales for each product item using quantity and price.
Grouping the data by store location.
Sorting the results by total sales in descending order.
Presenting the rankings with store location and total sales, starting with the highest sales.
Step 7: Showing Purchase Method by Gender Table
In this step, we create a table to display purchase methods by gender. We use an aggregation pipeline to group the data by gender and purchase method, and then present the results as a table. The Pandas library is used to format the data into a tabular structure for easy visualization.

Step 8: Showing Monthly Total Sales
Understanding how sales evolve over time is crucial. To achieve this, we calculate monthly total sales by creating an aggregation pipeline:

We start by unwinding the items array to access individual sales records.
Sales for each product item are computed based on quantity and price.
The data is grouped by year and month, utilizing the saleDate field.
The results are presented as monthly total sales, grouped by year and month, with full month names.
Step 9: Closing the Database Connection
Once we've completed our analysis and extracted valuable insights, it's important to close the database connection for proper resource management. We use client.close() to ensure that resources are released appropriately.

This article has demonstrated how to work with MongoDB and Python to perform data analysis on sales records. We've covered crucial steps, from setting up the environment to conducting meaningful analysis and visualization of the data. This approach can be applied to various scenarios where database-driven data analysis is required.
