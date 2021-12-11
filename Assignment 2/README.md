
# Assignment 2

## NYC Restaurants

We will analyze restaurant inspections in New York City, starting November 1, 2014 and ending January 31, 2015. The data is in the file NYC Restaurants.csv.
Setup First, read in this data using:

• df = pd.read csv(’NYC Restaurants.csv’, dtype=str).

This ensures that all fields are read in as strings, and loading the data is relatively fast.

**[Q1, 6 points] Create a unique name for each restaurant.** On the DataFrame created above, add a new column to your DataFrame, called ’RESTAURANT’, that combines DBA, BUILDING, STREET, ZIPCODE, and BORO fields. For example, “WENDY’S 469 FLATBUSH AVENUE 11225 BROOKLYN”. Print the first 10 values of the RESTAURANT column of your DataFrame.

**[Q2, 6 points] How many restaurants are included in the data?**
Careful now:
• A “Subway” in one particular address (i.e., building, street, zipcode, and boro) counts as one restaurant; don’t combine all Subways into one restaurant!
• The data can have multiple violations for the same restaurant!

**[Q3, 6 points] How many chains are there?** Let us define a chain to be the same restaurant name occurring in at least two different (building, street, zipcode, boro) addresses (i.e., one DBA with multiple restaurant locations). You’ll see multiple versions of the name ”DUNKIN DONUTS”. Just act as if they are different chains.

**[Q4, 6 points] Plot a bar graph of the top 20 most popular chains.** We already have the chains from the previous problem. Count the number of restaurants for each chain as a measure of its popularity.

**[Q5, 6 points] What fraction of all restaurants are chain restau- rants?** You should think of a restaurant as being one restaurant at one location. So “Wendy’s 5th Street” and “Wendy’s on 10th Street” are two different restaurants. Essentially a restaurant is what you defined in Q1.

**[Q6, 6 points] Plot the number of non-chain restaurants in each boro. First, we need to figure out all the non-chain restaurants, then select out only those restaurants, and finally plot the number of such restaurants by boro. Make sure to look at the plot; we don’t want to see... oh... the “missing” boro.

**[Q7, 8 points] Plot the fraction of non-chain restaurants in each boro.** The boro with the most non-chain restaurants might just be the boro with the most restaurants in general. If we want to find the boro that attracts the most “independent” restauranteurs, we must divide the number of non-chain restaurants by the total number of restaurants in the boro. Plot this. Is the boro with the most independent restaurants also the one with the highest ratio of independent restaurants?

**[Q8, 6 points] Plot the popularity of cuisines.** Which cuisines are the most well-represented among all restaurants? Define the popularity of a cuisine as the number of restaurants serving that cuisine. Plot the popularity of the top 20 cuisines.

**[Q9, 9 points] Plot the cuisines among restaurants which never got cited for violations.** Ideally, you should explore and see what happens when there is no violation, but here I will just tell you: the ’VIOLATION CODE’ field is missing.
First, find the restaurants that were never cited for a code violation. The compute the popularity of each cuisine among these “clean” restaurants. Plot the popularity of the top-20 among these cuisines.

**[Q10, 6 points] What cuisines tend to be the “cleanest”?**
• Select all cuisines for which there were at least 20 restaurants repre- senting that cuisine.
• For each such cuisine, compute the ratio of the counts in Q9 to Q8. This is the ratio of restaurants that never got cited, versus total number of restaurants, for each cuisine.
• Find the top-10 cuisines with the highest ratios; these are that cuisines whose restaurants are “most likely to be clean.”

**[Q11, 8 points] What are the most common violations in each borough?** Create a table of the number of times each violation description was observed in each borough, and figure out the most common violation description for each borough.
To create the table, check out the crosstab function. We will see a more general version of this when we discuss groupby in class.

