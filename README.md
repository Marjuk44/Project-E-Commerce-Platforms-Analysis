# Project-E-Commerce-Platforms-Analysis
Final Project for the Data Analytics Full Time Bootcamp (Jul'24) at Ironhack, Lisbon.

## Introduction

This project focuses on analyzing product prices and popularity across three major e-commerce platforms: Amazon.de, AliExpress, and Temu. Data was collected through web scraping for Amazon.de and AliExpress, and supplemented with a Kaggle dataset for Temu. The analysis targets the top 100 best-selling products from the five most popular online shopping categories. Results show significant differences in average prices across the platforms, as well as a strong correlation between product reviews and sales volumes. A customer survey conducted in Europe and North America further revealed that while Amazon maintains a dominant position, Temu is gaining traction in certain categories. The next phase of the project will involve developing a service or application that allows sellers to benchmark their products against competitors, and helps buyers easily compare product prices and popularity.

![Screenshot 2024-09-17 174042](https://github.com/user-attachments/assets/123562b3-9e15-47e5-beab-527906cc5695)


## 1st Step: Collecting Data
The first and the biggest challange faced for the project was data collecetion step. 

- While scrapping the sites, tey automatically detect our code as a "Bot" only after a few try.
- Configuring the function "time.sleep" and "random.uniform" played a vital role to not get detect as 🤖
- The code automatically read the whole catalog page, collect selected data and store them in a data frame.
- Selenium helps to fetch number of sold unit and/or number of product review from the product page.
- The code open each product page collect the data and driver.close to close the page.
- In some case the code needs to go to the second page and do the same thing again as first page.
- After 100+ failed attempt of web scrapping to the site Temu Kaggle dataset was only hope. It was keep asking to solve the captcha.


## 2nd Step: Preparing Data
Cleaning the collected data and wrangling them was an important part for this project. Initally the code collect 70 to 100 data point from each category for the store amazon and Ali Express. It stored in a csv file.

- Merging all the categorized product data (CSV files) to start cleaing.
- In the product price column there were currency symbol, whics was erased. 
- Replacing the "+" symbol to "" and as well as changing the "K" to "000" for the n_sold_unit column.
- Changing the data types as float for all columns except product title.
- Renaming and re ordering the column.
- Assigning the store Id and category id.
- For the Temu store we collect 100 best selling products in terms of number of sold units.
- From the data set we filter the chosen category and kept only selected columns.
- Checking and dropping duplicates and null values.
- Dropping and restting index where necessary.


## 3rd Step: Connecting Python to SQL

- Storing the data in cloud is a future upgrade for the project.
- Create a database for product detail, store and category in SQL.
- Setting primary key and foreign key to finalize the Entity Relationship Diagram
![image](https://github.com/user-attachments/assets/25cf6ac6-51b8-4035-8532-d3761cc0d1ae)


## 4th Step: KPI's
In order to understand the product popularity and variation in average prices, the key performance indicator decided for this project are:

- Average prices per category in each online store
- Number of sold units per category in each online store
- Number of product reviews in each online store.


## 5th Step: EDA & Dashboard

- Number of product taken per store and per category
- Checking the outliers for product price in each category
- Pearson & Spearman co-relation for prices vs reviews and prices vs sold unit (Negative and weak). Price increase reviews/sold units decrease.
- Positive co-relation between reviews vs sold unit. As one increase other one tends to increase as well.
- Distribution of prices among Amazon, Ali Express and Temu.
- Dashboard link: https://public.tableau.com/app/profile/marjuk.ahamed/viz/finalproject_17254881468690/Dashboard


## 6th Step: Hypothesis Testing

- A signaficant differnce between the online stores for their average product price. ANOVA test shows the P-value: 5.914670387683464e-12
- Product price is a strong predictor for number of sold units. Linear regressions shows the P-value: 0.00126
- Number of reviews is not a strong predictor of number of sold units. P-value: 6.492668731122193e-05 (OLS method)


## Final Step: Business Ideas
After analysing the data a few business idea rises for this project. In order to give strong reason to this ideas, a public survey has been conducted before the project deadline. 

- The seller among online stores can benchmark their position against competitor.
- The product popularity comparing application can really have a good impact.
- According to the survey there is a demand among user for this application.

### PPT file: https://www.canva.com/design/DAGP6GKwJYw/i7VNztw5GJiUe5OBCxbDfg/view
### Presentation link: https://youtu.be/5YjROacs1z8
### Survey responses link: https://docs.google.com/spreadsheets/d/1ToCmsEUezCyCtrjkPHtraO8FoQCqJDnHHXRfYKIZWfs/edit?usp=sharing



## Initial Improvement
- Create a .py file where all the webscrapping code stores
- A single ipynb file to load all the online stores product data by using the .py file
- After loading the data cleaning and preparing for the EDA
- Anoher ipynb file just to to the EDA

## Future Upgrade
- Webscrap amazon to extract n_sold_unit which conducted manually to save time before final submission.
- Keep fighting with Temu captcha to extract data from this website. 
