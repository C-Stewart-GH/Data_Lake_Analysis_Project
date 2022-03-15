<a name="BackToTop"></a>


# What is the difference and situational use of Data Lakes vs. Data Warehouses?

**Contributors: Cameron Stewart, Nathan Deinlein, Cleveland Johnson**

>The goal of this project is to address two foundational questions.  The first question is “What is the difference between the data warehouse and data lake?”.  Once grounded in the differences, we will then seek to address “When does it make sense to use a data lake instead of a data warehouse?”. There are high level statements and understandings of the use cases for these data repositories, but demonstrating the use through implementation will allow our team to highlight specific differences. In this project, the team created a Data Warehouse using MySQL and created a Data Lake using MongoDB. These created data repositories will be used to store Twitter data on tweets related to 'Data Lakes' and 'Covid-19'.

The information below is a summary and the full report can be downloaded [here](../main/Full%20Report/Final%20Report.docx).

---

## Table of Contents
- [Creating Data Warehouse](#P1)
- [Creating Data Lake](#P2)
- [Query Comparison](#P3)
- [Conclusion](#P4)
- [References](#References)

---

<a name="P1"></a>

## Creating Data Warehouse

To create a simple example Data Warehouse, the team created a single relational database in MySQL. Using Python packages mysql.connector and tweepy, the team was able to automatically pull 81 tweets related to 'covid-19' in a specific date range into the MySQL database. Jupyter Notebook used to pull in the data can be found [here](../main/Jupyter%20Notebooks/Twitter%20API%20to%20SQL%20DB.ipynb).

This database had a single table that only stored:
- idTweets
- Created_At
- Tweet

When attempting to bring in the semi-structured tweet data, MySQL created some errors due to the missing data. This would prove to be less of a concern in a NoSQL Database and Data Lake. Further details can be found in the [full report]((../main/Full%20Report/Final%20Report.docx)).

[Back to Top](#BackToTop)

---

<a name="P2"></a>

## Creating Data Lake

Document walking through the creation of the Data Lake [here](../main/Walkthrough%20of%20Created%20Data%20Lake/Data%20Lake%20Walkthrough.docx).

To create a simple example Data Lake, the team first created two NoSQL document databases in MongoDB. The first database imported the Covid-19 Twitter data that was pulled into MySQL above. The second database used Python packages tweepy and pymongo to automatically pull 62 tweets related to 'data lakes' within a specified date range. Jupyter Notebook used to pull in the data can be found [here](../main/Jupyter%20Notebooks/Gather_Tweets_and_Upload_to_MongoDB.ipynb).

Next, the team configured an Atlas Data Lake that feeds in data from both databases. Each database features did not match and this is acceptable in a Data Lake. This is because Data Lakes allow an unstructured data extract and the transformation of the data into an organized format will occur at the point when the data is needed. In a Data Warehouse, this would not be possible because the data must be in a consistent structured format.

Configuration of Data Lake:

<img width="700" alt="image" src="https://user-images.githubusercontent.com/37990637/158467695-faacccdb-b2f2-4718-9474-f5905f093cee.png">

Example of data in Data Lake:

<img width="700" alt="image" src="https://user-images.githubusercontent.com/37990637/158467632-54ba39b4-036e-48eb-b165-aea47dd737dc.png">

[Back to Top](#BackToTop)

---

<a name="P3"></a>

## Query Comparison

In order to access the Data Lake, the team used MongoDB Compass and queried the data using MongoShell. This query searches all the documents from both databases for occurances of the word "data" and a retweet count of 0.

Example Query and Output from Data Lake:

<img width="700" alt="image" src="https://user-images.githubusercontent.com/37990637/158487235-7d129ec4-9c64-4513-b0c5-df034c8eaeb1.png">

To query the MySQL Database, the team used SQL. The team queried for 'Covid-19 vaccine' in the records of the single database. Notice, the team is not able to query across multiple differently structured databases in this instance.

Example Query in MySQL Database:

<img width="700" alt="image" src="https://user-images.githubusercontent.com/37990637/158488114-d0071595-2c85-4bf9-855d-30e598d7239c.png">


[Back to Top](#BackToTop)

---

<a name="P4"></a>

## Conclusion

What is the difference between a data warehouse and a data lake?

We observed a stark contrast between the data warehouse and data lake in terms of the structure of the data.  In the case of the data warehouse, we had to analyze initial data pulls from the Twitter API, discuss available fields, determine what question we wanted to answer with a query and then align on the table structure of the database.  This made us realize how accurate the schema on write moniker was for a data warehouse. While for the data lake, we merely had to capture the desired variables from the Twitter API, load them into a data frame and load them into the database. Based on these observations, the unstructured data ability of the data lake enabled speed of discovery, ingestion, and integration with other data sets. While this may appear to shift the work that it takes to transform data down the line, it specifically puts the ability to transform the data in a useful format in the hands of the person that has the business knowledge to make an informed decision. The data lake is made to handle large amounts of data when compared to the data warehouse. 

When does it make sense to use a data lake instead of a data warehouse?

When to use a data warehouse and a data lake can easily be summarized in terms of the problems being solved by the system. A data warehouse should be used where the solution is known for the problem and accessed routinely for operational decision.  An example of this would be start of day reports for investment bankers.  These users have a core set of known data that is aggregated from multiple systems and show historical information to prepare them for the start of the trading day. A data lake should be used when we still do not know the solution for the problem or are improving an existing solution.  This would require the discovery, ingestion, and wrangling of data to better understand the current state and present potential solutions for further analysis.  This approach would benefit from speed and flexibility provided by the data lake data platform. A good analogy often used to compare these concepts of data warehouse vs data lake is “agriculture vs. hunting/gathering”.

[Back to Top](#BackToTop)

---

<a name="References"></a>

## References

[Full Report](../main/Full%20Report/Final%20Report.docx)

[Fetch Twitter sata and transfer to MongoDB](../main/Jupyter%20Notebooks/Gather_Tweets_and_Upload_to_MongoDB.ipynb)

[Fetch Twitter sata and transfer to MySQL](../main/Jupyter%20Notebooks/Twitter%20API%20to%20SQL%20DB.ipynb)

[Data Lake Creation Walkthrough](../main/Walkthrough%20of%20Created%20Data%20Lake/Data%20Lake%20Walkthrough.docx)

##### Technologies:

Jupyter Notebook

Python 3.7.7

MongoDB

MongoDB Compass

MySql

[Back to Top](#BackToTop)
