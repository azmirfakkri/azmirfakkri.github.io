---
layout: post
title: What is Data Science?
thumbnail: "assets/img/pexels/datsci-ko.jpg"
tags: [Statistics, Technology, Industry]
---

Coming from a medical/healthcare background, I had very little to expect when I started a data analytics course last October. However, having completed three blocks of lectures and exams, it started to become very clear what data science is to me. Since this is a new field, it is difficult to pinpoint what exactly data science is. Of course you will be dealing with data, but what else involved beyond data?

There are three main components to data science, rank based on importance and is non-exhaustive:
1. Statistics
2. Technology
3. Domain or industry knowledge

## Statistics

Between statistics and technology, I put statistics as the most important aspect in data science, simply because the implementation of the concepts that you learn in statistics are done using technology (more explanation about technology in the next paragraph). Note that this opinion is based on my journey in data science and does not apply to everyone in data science.

At the very basic level, it is important to understand the difference between central measures and spread measures as you will be dealing with these in advanced analytics. I had my first lesson in statistics when I was doing International Baccalaureate Diploma for Higher Level Mathematics. I did not enjoy statistics back then, the module was badly taught by a lecturer who explained very little and expected us to be able to do all the calculations five minutes into the first lesson.

I am so glad to get the opportunity to learn statistics again and to get hands-on experience in modelling data using one of the many probability distributions. I found it very interesting the fact that you can do this in statistics and make an objective decision using hypothesis testing.

You can argue that a data engineer can still produce excellent deliverables without knowing a lot of statistics, and this is absolutely correct. However, as data science is a big field, of course there will be different roles associated with it, for example, data engineer and machine learning experts. Machine learning experts will have an extensive understanding of statistics to help them evaluate the models that they develop, while a data engineer is heavy on the software engineering side to create a data pipeline.

## Technology

When I mentioned technology, I wasn't exactly referring to a scientific calculator. There are so many programming languages and tools in data science coming with their own advantages and disadvantages. As you gain more experience in data science, you will have a suite of your go-to technology depending on what you're comfortable with and as required by the projects you are working on.

To further discuss about technology in data science, let's divide it into four categories.

**1. Programming Languages**

There are many programming languages that can be used as an analytic language. The two most popular languages are R and Python. You can compare R and Python for data analysis from this [infographic](https://www.datacamp.com/community/tutorials/r-or-python-for-data-analysis) published by DataCamp. Scala is another programming language that is used for [Apache Spark](https://spark.apache.org) but it is not an exclusive language for Apache Spark as you can write your codes using Python, [PySpark](https://spark.apache.org/docs/0.9.0/python-programming-guide.html) and R, [SparkR](https://spark.apache.org/docs/latest/sparkr.html). MATLAB is a language that is very similar to R, if you know R, it is most likely you can learn and write in MATLAB within an hour.

I think it is very useful to learn R and Python as they have many libraries that can assist you in your analysis. One thing to note, in some job descriptions, HR or recruiters will list the library or package names for example ggplot2 or SciKit-Learn. ggplot2 is a data visualisation package in R and it is very popular in creating stunning graphs and charts. SciKit-Learn on the other hand is a Python package for machine learning. So these are not something separate from R or Python, they are just packages written in R or Python.

**2. Query Languages**

The most popular query language is Structured Query Language (SQL). A query language is used to query a database to retrieve information. SQL is used for relational database where data is stored in tabular format with row and columns. Database that is not relational is called NoSQL (Not Only SQL) database. An example of a NoSQL database is Neo4j, a graph based database and the its query language is called Cypher.

**3. Data Science Tools**

As I mentioned before, there is a lot of data science tools available on the market, either open source or proprietary. The ones listed here are only a tiny fraction of what's available.

<span style="color:#2980B9">**Tableau**</span>  
Tableau allows you to analyse your data and create visualisations and dashboards with little to zero line of code. These dashboards can be shared and embedded on the web to be shared with other users. Experience and skills in Tableau are desirable in data science job market.

<span style="color:#2980B9">**PowerBI**</span>  
A Microsoft product similar to Tableau.

<span style="color:#2980B9">**Rapid Miner**</span>  
Rapid Miner, a GUI-based application, lets you build a predictive model within minutes with just a few clicks of button. I am not a fan of Rapid Miner as the model you develop becomes a little bit like a "black box", you don't know what's going on under the hood. It is probably suitable for users who does not know how to build predictive models in programming language.

<span style="color:#2980B9">**Neo4j**</span>  
A graph based database, using Cypher as a query language. It is probably a great idea to learn Neo4j as graph analytics are getting more attention.

<span style="color:#2980B9">**Microsoft SQL Server Management Studio**</span>  
Microsoft SQL Server Management Studio is an integrated environment which allows you to manage SQL infrastructure. Codes are written in SQL.

**4. The Apaches**

The Apache Software Foundation's mission is to provide software for the public good. They have numerous open source projects. You might see some of Apache's open source projects in many job descriptions. The most commonly seen is Apache Hadoop. But let's sort these projects by two categories that are closely related to data science.

<span style="color:#2980B9">**For Big Data**</span>  
    * [Ambari](https://projects.apache.org/project.html?ambari)
    * [Kafka](https://projects.apache.org/project.html?kafka)
    * [Spark](https://projects.apache.org/project.html?spark)
    * [Sqoop](https://projects.apache.org/project.html?sqoop)
    * [Zeppelin](https://projects.apache.org/project.html?zeppelin)

<span style="color:#2980B9">**For Databases**</span>  
    * [Cassandra](https://projects.apache.org/project.html?cassandra)
    * [Hadoop](https://projects.apache.org/project.html?hadoop)
    * [HBase](https://projects.apache.org/project.html?hbase)
    * [Hive](https://projects.apache.org/project.html?hive)
    * [Pig](https://projects.apache.org/project.html?pig)
    * [ZooKeeper](https://projects.apache.org/project.html?zookeeper)

You will probably use half of the tools listed here, so it is good to know what they are and their functions.

## Domain/Industry Knowledge

What I really meant by domain or industry knowledge is the type of data that you will deal with. For example, in healthcare analytics, a data science will deal with health records or blood pressure measurement throughout the day for a cohort of patients. In a bank, they might have an analytics department focusing on customer analytics or marketing analytics.

It will definitely put you to a good advantage having the knowledge or background about the industry that you are working in but looking at it from an analytics perspective.
