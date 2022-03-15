<a name="BackToTop"></a>


# What is the difference and situational use of a Data Lake vs. a Data Warehouse?

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

To create a simple example Data Lake, the team first created two NoSQL document databases in MongoDB. The first database imported the Covid-19 Twitter data that was pulled into MySQL above. The second database used Python packages tweepy and pymongo to automatically pull 62 tweets related to 'data lakes' within a specified date range. Jupyter Notebook used to pull in the data can be found [here](../main/Jupyter%20Notebooks/Gather_Tweets_and_Upload_to_MongoDB.ipynb).

Next, the team configured an Atlas Data Lake that feeds in data from both databases.

Configuration of Data Lake:

<img width="700" alt="image" src="https://user-images.githubusercontent.com/37990637/158467695-faacccdb-b2f2-4718-9474-f5905f093cee.png">

Example of data in Data Lake:

<img width="700" alt="image" src="https://user-images.githubusercontent.com/37990637/158467632-54ba39b4-036e-48eb-b165-aea47dd737dc.png">

[Back to Top](#BackToTop)

---

<a name="P3"></a>

## Query Comparison

In order to access the Data Lake, the team used MongoDB Compass and queried the data using MongoShell.


[Back to Top](#BackToTop)

---

<a name="P4"></a>

## Conclusion

[Project 4](../main/Project%204/Project_4.ipynb)

Using Python's NLTK and Flair packages, I compared the accuracy of Part of Speech taggers for each tool on complex sentences. The Flair package proved to be the more accurate tagger in this project.

[Back to Top](#BackToTop)

---

<a name="References"></a>

## References




##### Technologies:

Jupyter Notebook

Python 3.7.7

MongoDB

MongoDB Compass

MySql

[Back to Top](#BackToTop)
