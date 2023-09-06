# nosql-challenge

# Eat, Safe, Love

## Task

The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. You've been contracted by the editors of a food magazine, Eat Safe, Love, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

## Part 1: Database and Jupyter Notebook Set Up

1. Import the data provided in the establishments.json file from your Terminal. Name the database uk_food and the collection establishments. Copy the text you used to import your data from your Terminal to a markdown cell in your notebook.

2. Within your notebook, import the libraries you need: PyMongo and Pretty Print (pprint).

3. Create an instance of the Mongo Client.

4. Confirm that you created the database and loaded the data properly:

List the databases you have in MongoDB. Confirm that uk_food is listed.
List the collection(s) in the database to ensure that establishments is there.
Find and display one document in the establishments collection using find_one and display with pprint.

5. Assign the establishments collection to a variable to prepare the collection for use.

## Part 2: Update the Database

1. An exciting new halal restaurant just opened in Greenwich, but hasn't been rated yet. The magazine has asked you to include it in your analysis.

2. Find the BusinessTypeID for "Restaurant/Cafe/Canteen" and return only the BusinessTypeID and BusinessType fields.

3. Update the new restaurant with the BusinessTypeID you found.

4. The magazine is not interested in any establishments in Dover, so check how many documents contain the Dover Local Authority. Then, remove any establishments within the Dover Local Authority from the database, and check the number of documents to ensure they were deleted.

5. Some of the number values are stored as strings, when they should be stored as numbers.

1. Use update_many to convert latitude and longitude to decimal numbers.
2. Use update_many to convert RatingValue to integer numbers.
 
## Part 3: Exploratory Analysis

Eat Safe, Love has specific questions they want you to answer, which will help them find the locations they wish to visit and avoid.

Use the following questions to explore the database, and find the answers, so you can provide them to the magazine editors.

Unless otherwise stated, for each question:

Use count_documents to display the number of documents contained in the result.

Display the first document in the results using pprint.

Convert the result to a Pandas DataFrame, print the number of rows in the DataFrame, and display the first 10 rows.

Which establishments have a hygiene score equal to 20?

Which establishments in London have a RatingValue greater than or equal to 4?

What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?

How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas.

## Description

I started by cleaning and setting up the database for analysis using the NoSQL setup starter jupyter notebook provided. I imported the dependencies, created an instance of MongoClient, and checked the database was created. I assigned the newly created databse to a variable, checked the collections of the database and assigned the collection to a variable as well. I updated the database with a newly opened restaurant according to the details provided. I determined the business type id for the restaurant/cafe/canteen business type. I updated the newly opened restaurant with its correct business type id. I then confirmed the number of establishments with the local authority name as Dover and deleted them from the Database. I updated the datatype for the latitude and longitude to be decimals and the rating values to be integers. 

For the analysis, I used the NoSQL analysis starter notebook provided. I assigned the database and collection of the database to respective variable names to use in the analysis. I wrote a query for the establishments with a hygiene score of 20, counted the number of establishments using .count_documents, and displayed the first result from the query using pprint. I then coverted the results from the query to Pandas DataFrame and displayed both the first ten results of the DataFrame and total number of rows. For the second query, using the '$regex' function to find the local authorities which contatined London in their name and the '$gte' function specifying for these establishments to have a rating value greater than or equal to 4, I counted the total number of establishments and printed the first document that met this criteria. I converted these results to a DataFrame and displayed both the total number of rows and first ten results of the Dataframe. To find the top five establishments with a rating value rating value of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours", I first took the longitude and latitude from the NoSQL setup starter notebook for Penang Flavours. I then wrote a query to find the establishments within the degree score provided using the '$lte' and '$gte' functions adding and subtracting respectively from the longitude and latitude. I sorted these results by the establishments with the lowest hygiene scores. I printed the results using the query, sort, and limited to the first 5 results. I then converted these results to a DataFrame. To determine how many establishments in each Local Authority area have a hygiene score of 0, I wrote a match query to match all the establishments with a hygiene score of 0. I grouped the local authorities by count of the total sum of each local. Sorted the count in a descending fashion. Created a pipeline to list the results. I printed the total number of results as well as the first ten results. I then converted these results to Dataframe.   
