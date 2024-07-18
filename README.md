# Marvel-Mart-Python

# Summary

You have been recently hired by Marvel Mart, one of the world's leading department store chains, to be their new data analyst. You were hired because of your technical skills with Python. Immediately, they offer you a CSV file and ask you to provide specific business analytics based on the data.   

You are allowed required to use Python and the numPy and pandas libraries for this project. You may use any other Python libraries that you would like as well. 

 Please take a few moments to familiarize yourself with the CSV file called  MM_Sales.csv

Download MM_Sales.csv  Notice the columns, the headings, the format of the data in each column.   

Marvel Mart has been providing both online and offline sales of a variety of  products for many years. The provide services to countries all over the world and have stores in many countries. Marvel Mart divides their order up by an alphabetical priority labeling system: 

    C: Critical (most essential to be delivered quickly and accurately) 

    H: High 

    M: Medium 

    L: Low 

There are several columns of data for sales: 

    Unit Price: money collected for sale of 1 unit 

    Unit Cost: money spent for purchase of 1 unit 

    Total Revenue: money collected for sale of the collection of units 

    Total Cost: money spent for purchase of the collection of units 

    Total Profit: Total Cost - Total Revenue (profit)      

The rest of the columns should be self-explanatory. 

 
# Deliverables

When I run your script, I expect the output to make sense. You may have print statements which print things - I hope you do. But I want when I look at it to know what I am looking at so you should always print a line explaining what the output is. You are not REQUIRED to have output when I run the script other than the CSV and TEXT files I am requiring.

When you submit your project, it should contain these below. Do not zip these files and submit.

    Python script of complete code. Submit as .ipynb format.
    PDF or HTML version of the .ipynb file
    MM_Sales_clean.csv
    Marvel_Mart_Rankings.txt
    Marvel_Mart_Calc.txt
    Countries_By_Region.csv
    Documentation surrounding your design process. Please submit this as a Word document. Documentation will just be an explanation in your own words of the process you took to create the Python script. Start with how to figured out to do the data cleaning and write about each part.

 
# The Report Questions
Outline
Part 1: Cleaning the Data
Part 2: Exploratory Data Analysis with Reports & Visualizations

1. Country Rankings

2. Count of Sales Channels & Order Priorities

3. Profits by Item Type

4. Descriptive Statistics
Part 3: Cross-referencing the Data

 
# Part 1: Cleaning the Data

"It came to our attention that some of the data were either incorrectly entered or missing entirely! This is going to throw off our calculations if it is left unchecked. We were grateful to discover none of it happened in our accounting columns of the data for that would be very detrimental but we aren't sure where the missing/incorrect data is elsewhere. Here's what we do know to help your investigation to find the missing/incorrect data. Of the columns that we have, we know the missing/incorrect data comes from these columns"

    Country   (either missing AND/OR will be a number as a string)
    Item Type   (either missing AND/OR won't be a valid Item Type from the other ones listed)
    Order Priority   (either missing AND/OR won't be a valid priority code of 'C', 'H', 'M', 'L', or 'NULL')
    Order ID   (either missing AND/OR won't be a number)

Note: invalid Item Type in this case will have only one instance of that invalid Item Type. Usually, a list of valid item types would be supplied.
If you find incorrect/missing data and its text type for that column, change it to the string "NULL".
If you find incorrect/missing data and its a number type for that column, change it to 0. (or 0.0 if its a float).

Once you find all the incorrect and missing values and replace them with "NULL" or 0, then you need to remove all rows that have been altered.
You need to change the values, then rewrite to a new CSV file called MM_Sales_clean.csv so it can be used later with the correct values.

 

Hints:

    Test for missing values FIRST then if you find the ones that are missing, you don't have to test those for incorrect values.
    doing large number sums with floats in Python usually produces scientific notation but we don't want that. You can turn that off by putting the following line under the import statements at the start of the script: pd.set_option('display.float_format', lambda x: '%.3f' % x
    While it is possible and acceptable to produce a non-pandas using solution, I would suggest that you use pandas Dataframes for this. It makes a difficult job much easier. The guide to how to do that is here and some other resources:

    https://www.geeksforgeeks.org/working-with-missing-data-in-pandas/ 

Links to an external site.
https://www.geeksforgeeks.org/python-read-csv-using-pandas-read_csv/
Links to an external site.
https://www.geeksforgeeks.org/saving-a-pandas-dataframe-as-a-csv/

    Links to an external site.

You will need to google things to get this done. Part of being a programmer is knowing how to find solutions on the internet and adapting them.)

 
# Part 2: Exploratory Data Analysis with Reports & Visualizations

"First, we would like you to get us some general statistics from the data."

    "We want to know which countries we sell the most so we can pick a new location to build a shipping center. Rank the Top 10 countries we sell to the most to least along with the number of sales we've had with that country." (note you are getting a count of the number of sale transactions here not the sum of the total sales)
        Use Seaborn or Matplotlib to create a chart of your choice showing these top 10 values by country.
            We have shipping centers in Trinidad and Tobago, Guinea, and Maldives right now. Which country should we build a shipping center in based on most sales and lack of shipping center? When I say most sales, I'm talking about the most sales transactions, not the most sales amount. A sales transaction is represented by a row. Please justify your reasoning.
        Write the results to a text file called MM_Rankings.txt.
            Be sure to use append so that you can append data rather than writing over top of the previous data.
            Include a newline between each append to the file.
            When writing to the file, please output in a text form such as: 

            Countries Most Sale Transactions:
            (Country Name): (number of sales transactions)
            (Country Name): (number of sales transactions)
            ...
            (Answer question) "The country we should build our shipping center is ______ because ____..."

    "Now we will need you to determine how many online and offline orders that our company takes. Also, if you could let us know the count of the different Order Priority types, that would be great. Please show us this in a pie chart format."
        Determine the count for how many online and offline orders we take.
        Determine the count of the different Order Priority types.
        Create a pie chart for each showing the differences in values (use Seaborn or Matplotlib).
        Add the results of the sales channel types and the order priorities to the file MM_Rankings.txt.
            Be sure to use append so that you can append data rather than writing over top of the previous data.
            Include a newline between each append to the file.
            When writing to the file, please output in a text form such as: 

            Sales Channels:
            Online: ####
            Offline: ####
            We do more online/offline sales.

            Order Priorities: 
            L: ###
            M: ###
            H: ###
            C:  ###
            We do more L/M/H/C order priorities.

    "For our next section, we will need you to give us an idea of how well our Item Types are producing profits for us. At the end, report to us which 3 item types are providing the most profit."
        Create a Boxplot using Seaborn showing the Total Profits DISTRIBUTION by Item Type.
        Use Python to determine the sum of Total Profit by Item Type.
        Now create a chart type of your choice (Seaborn or Matplotlib) showing the sums of the different Item Types.
        Now, using Python, rank the top 3 item types we did the most sales (brought in most profit) in to the least sales. (Use 'Total Profit' to determine this).  Please list the item types and the amount of profit made from sales.
        Add the results of the top 3 item types to the file MM_Rankings.txt.
            Be sure to use append so that you can append data rather than writing over top of the previous data.
            Include a newline between each append to the file.
            When writing to the file, please output in a text form such as: 

            Highest Selling Items:
            Item 1: ####
            Item 2: ####
            Item 3: ####
            We profited from ________ the most.
        Provide a markdown section discussing the results of the boxplots. Discuss what is being shown in the boxplots amd do some business analytics around what sort of use this sort of chart might help in making decisions. Are there any unexpected results? Discuss them.

    "Finally, we need you to determine some descriptive statistics for us. Please determine the sum, average and maximum values for the Units Sold, Unit Cost, Total Revenue, Total Cost and Total Profit. Please put this in a report."
        Produce the data above for the sum of the requested columns.
        Produce the data above for the average of the requested columns. (Average Units Sold, Average Cost, etc)
        Produce the data above for the maximum of the requested columns. (Max Units Sold, Max Cost, etc.)
        Create two line plots using Seaborn or Matplotlib, one for the sums and one for both the averages and the maximums. DO NOT INCLUDE UNITS SOLD OR UNITS COST.
        Now you will save these calculations below to a text file called MM_Calc.txt. When writing to the file, please output format such as:


Sums:
Units Sold: (Number)
Unit Cost: (Number)
Total Revenue: (Number)
Total Cost: (Number)
Total Profit: (Number)

Averages:
Units Sold: (Number)
...

Maximums:
Units Sold:
...

 
# Part 3: Cross-Reference Statistics

"We are in desperate need of a concise list of the Regions we sell to with the Countries that are located in each one."

For this part you will be cross-referencing the data in the CSV file and the getting an output and writing it to a new CSV file. 

    Please get a list of the Regions and then the countries we sell to in that region. Please be sure no duplicates Regions or countries exist.
        (Does not have to be done this way)
            Non-pandas Solution advice: Please return this as a dictionary of lists with the keys of the dictionary being the name of each Region and the list attached to that being all the countries we sell to for that region. You may also return it as a Series of Lists (although I found that to be harder).
            Finally, if you want to use an alternate method with pandas Dataframes, that will be accepted as well. Be sure your output is easy to read and your code makes sense.
    Write this out to a CSV file called Countries_By_Region.csv.
        (Be careful here as there is a header row when you convert the csv to a dictionary. If you end up getting the header row in your final result, just remove it. You are free to do it however you want as long as in the end its a dictionary of lists (or Series of Lists), the keys being the Regions and then the list for that key being the countries that is sold to, with no duplicates. And then print it to the csv file.)

Your CSV file should look like below. Order of Regions and Countries is unimportant but structure should be the same. Here are the counts for the countries by Region:

North America: 4, Europe: 48, Asia: 27, Australia & Oceania: 15, Central America & The Carribean: 20, Sub-Saharan Africa: 48, Middle East and North Africa: 23

 

MarvelMartScreenShot.png  




The task items to be graded are broken down as: (total of 23 tasks)

Part 1

4 Data Cleaning: Country, Item Type, Order Priority, Order ID

Part 2

1.1, 1.2, 2.1, 2.2, 2.3, 2.4, 3.1, 3.2, 3.3, 3.4, 3.5, 3.6, 4.1, 4.2, 4.3, 4.4, 4.5, 

Part 3

1.1, 1.2
