# **Basic-Descriptive-Analytics-with-Python**

In this analysis I asked initial exploration questions that are aimed to help us build our understanding of the data. The data I used came from North York University (Ontario, Canada) and include IBMStock.csv, GEStock.csv, ProcterGambleStock.csv, CocaColaStock.csv, BoeingStock.csv. The files contain information about Date: the date of the stock price, always given as the first day of the month, and StockPrice: the average stock price of the company in the given month.

## **1.Warm-up/Basic statistics Questions:**

1.	How many rows of data are in each dataset?
2.	What is the earliest/latest year in our datasets?
3.	For the period above what is the average stock price of Coca Cola?
4.	What is the maximum price of IBM during this period?
5.	What is the standard deviation of P&G stock price over this period?
6.	What is the median price of Boeing in the last 5 years for which we have data?

![image](https://user-images.githubusercontent.com/95148782/165419372-52763c66-1312-4990-9a5d-cf6c4947383d.png)
![image](https://user-images.githubusercontent.com/95148782/165419439-756d22f8-318a-47eb-8bc9-e6bc5f84d153.png)

I checked all datasets in the same way as IBM:
    - each dataset contains 480 rows
    - in each dataset the earliest year is 1970, latest year is 2009
    - in each dataset Data field has "object" dtype and should be converted into “date” data type
To answer the questions, I applied mean, shape, head, tail, and describe functions to the dataframes and filtering by date. 
![image](https://user-images.githubusercontent.com/95148782/165420357-a0bef177-a210-4cdf-86cc-4018a6665735.png)

![image](https://user-images.githubusercontent.com/95148782/165420372-453f4989-94c8-4d24-a90e-da277c9b4545.png)

![image](https://user-images.githubusercontent.com/95148782/165420387-ee0cbc67-1735-4198-80d6-3e14cd8402bc.png)

## **2.Basic Plotting Questions**

One way to enhance our understanding of data is through visualization. I plotted the StockPrice of Coca-Cola on the Y-axis across Date on the x-axis answer to answer the following questions: 
1. During which year did Coca-Cola has the highest/lowest stock price?
2. What calendar year did it look to have the biggest (Year-over-Year) percentage increase? 

![image](https://user-images.githubusercontent.com/95148782/165420509-64ffd0ea-65f3-493d-94fe-4aacfd82e6a2.png)

![image](https://user-images.githubusercontent.com/95148782/165423370-8232bdd5-ae04-46ee-a282-addf0dd56f5f.png)


-	CocaCola had the highest stock price in the end of 1972
-	CocaCola had the lowest stock price in the beginning of 1980
-	Y-O-Y percentage increase=(stock price at the end of year - stock price at the end of last year )/stock price at the end of last year. CocaCola looks to have had the biggest Y-O-Y percentage increase in 1982-1983 period (around 150%)

Next, I added P&G stock price onto the same graph and answered the following question to compare two different stocks:
1.	Which company’s stock dropped more (relatively – i.e. percentage-wise) in March of 2000 when the stock market plummeted as the tech bubble burst?
2.	In the year (i.e. 1983) which company stock was going up? Which was going down?
3.	Across the entire time period shown in the plot which stock had a generally lower price?

![image](https://user-images.githubusercontent.com/95148782/165420875-e4b8f7ce-d23d-40bd-9c74-49139a6f07ee.png)
![image](https://user-images.githubusercontent.com/95148782/165423294-7c8086f1-11a6-4691-8f3c-96d9ff0dbb8d.png)


- In March 2000 PG's stock dropped almost twice as much as CocaCola's stock did (about 40% and 25% respectively)
- In 1983 CocaCola's stock was going up in average, and PG's stock was going down
- Generally,CocaCola's stock had a lower price across 1970-2010 period

## **3.Data Visualization for a specific period**

Instead of looking at the plot across the entire date range, I wanted to see what’s happening between 1995-2005 and answer the following questions:
1. Which stock price fell the most right after the tech bubble of March 2000?
2. What stock had the highest maximum price between 1995-2005?
3. A few years before the tech bubble of 1997, there was another stock market crash trigged by economic crisis in Asia in October of 1997. If compare stock prices from September 1997 to November 1997, which companies saw a decrease in price? Which company experienced the biggest decrease?
4. Which stock seemed to provide the best return (i.e. increase in price) between 2004-2005?
5. Between 1995-2005, which company had the biggest delta between the maximum and minimum stock price?
6. Which two companies’ stock price seem to be the most correlated (i.e. move up/down together)?

![image](https://user-images.githubusercontent.com/95148782/165423494-708d4631-2174-44a0-a26c-0e9c7bc32ba1.png)

-	GE stock price fell most after the tech bubble of March 2000
-	IBM had the maximum price in 1995-2005 period
-	PG,Boeing and CocaCola saw a decrease in price from Sep 1997 to Nov 1997. PG experienced the biggest decrease
-	Boeing seemed to provide the best return in 2004-2005 period
-	IBM had the biggest delta between max and min stock prices in 1995-2005
-	IBM's and GE's stock prices seem to be the most correlated

## **4.Monthly Trend Analysis**

I wanted to see if there are any monthly patterns (i.e. consistently higher/lower prices at various months of the year). To do for each company, I essentially wanted to compare “mean” by month vs the overall mean across the entire date range:
- I found find overall average stock price for each dataset and consider it as 100%
- Create a new variable 'Dynamic_ave' = stock price/(average stock price/100). If the result >100 it's over-indexing 
-  Find mean of stock price and dynamic average for each month across the entire datasets

![image](https://user-images.githubusercontent.com/95148782/165422535-5ded6d6c-3700-4707-a33b-1ddb950c2592.png)

IBM historically had an over-indexing in January-May period with the most over-indexing in February.

Applying the same approach to other stocks data I found the following patterns:

-	All companies have higher stock prices during the first half of the year comparing to the second one
-	All companies have increasing in stock prices in January comparing to December stock prices
-	CC and GE both have the most over-indexing in April
-	IBM and GE both have January-May over-indexing period
-	PG and Boeing both have shorter over-indexing period comparing to other companies (two months)

