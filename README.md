<a name="BackToTop"></a>


# What is the difference and situational use of a Data Lake vs. a Data Warehouse?

**Contributors: Cameron Stewart, Nathan Deinlein, Cleveland Johnson**

>The goal of this project is to address two foundational questions.  The first question is “What is the difference between the data warehouse and data lake?”.  Once grounded in the differences, we will then seek to address “When does it make sense to use a data lake instead of a data warehouse?”. There are high level statements and understandings of the use cases for these data repositories, but demonstrating the use through implementation will allow our team to highlight specific differences. In this project, the team created a MySQL Database to act as a Data Warehouse and created a Data Lake using MongoDB. These created data repositories will be used to store Tweets related to 'Data Lakes' and 'Covid-19'.

Below, is a summary and the full report can be downloaded [here.](../main/Full%20Report/Final%20Report.docx)

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

[Project 1](../main/Project%201/Project_1.ipynb)

This project looks at the interaction between lexical diversity and vocabulary size at multiple reading levels. The text was tokenized using Python's NLTK package. Books analyzed were found at: [Project Gutenberg](http://www.gutenberg.org/ebooks/bookshelf/215).

[Back to Top](#BackToTop)

---

<a name="P2"></a>

## Creating Data Lake

[Project 2](../main/Project%202/Project_2.ipynb)

This project develops a normalized score for both the vocabulary size of text and the long word vocabulary size of text. Using the mean of these normalized scores, I developed a text difficulty score that was tested across multiple reading levels. The project showed the created text difficulty score increased with the reading level. The text was tokenized using Python's NLTK package. Books analyzed were found at [Project Gutenberg](http://www.gutenberg.org/ebooks/bookshelf/215).

[Back to Top](#BackToTop)

---

<a name="P3"></a>

## Query Comparison

[Project 3](../main/Project%203/Project_3.ipynb)

This is a simple project with two parts. Part 1 - Stemmed Book Titles were tested for interpretability with another user. Part 2 - Compare examples in terms of % difference when you stem vs. lemmatize text. The text was tokenized, stemmed, and lemmatized using Python's NLTK package.

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
