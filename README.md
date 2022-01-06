# ShopifyDataScienceChallenge

Summer 2022 Data Science Intern Challenge 

Please complete the following questions, and provide your thought process/work. You can attach your work in a text file, link, etc. on the application page. Please ensure answers are easily visible for reviewers!

# Question 1: Given some sample data, write a program to answer the following: click here to access the required data set
Please see the code attached which includes visualizations and methods used to solve the problem!
On Shopify, we have exactly 100 sneaker shops, and each of these shops sells only one model of shoe. We want to do some analysis of the average order value (AOV). When we look at orders data over a 30 day window, we naively calculate an AOV of $3145.13. Given that we know these shops are selling sneakers, a relatively affordable item, something seems wrong with our analysis.

    1(i) Think about what could be going wrong with our calculation. Think about a better way to evaluate this data
            When there are outliers in a dataset, the median and interquartile range are used to summarize a typical value and the variability respectively. So to evaluate this             dataset  would be to use median statistical method that is more robust to outliers.The new median will be for Interquartile Range of the dataset for middle 50%                 values.
            
     1(ii) What metric would you report for this dataset?
            Use of median on the middle 55% of the dataset. 
            This makes to consider values that are not too high or low.
     1(iii) What is its value
            292.5
         
         
  # Question 2: For this question you’ll need to use SQL. Follow this link to access the data set required for the challenge. Please use queries to answer the following questions. Paste your queries along with your final numerical answers below.
  
   2(i) How many orders were shipped by Speedy Express in total?
         select count(Orders.OrderID) as 'Speedy Express Count' from Orders INNER JOIN Shippers on  Orders.ShipperID=Shippers.ShipperID where Shippers.ShipperName = 'Speedy              Express';
         
         54
         
   2(ii) What is the last name of the employee with the most orders? 
           select top 1 Employees.LastName from Orders INNER JOIN Employees on Orders.EmployeeID=Employees.EmployeeID group by Employees.LastName order by                                Count(Orders.OrderID desc;
   
           Peacock
    2(iii) What product was ordered the most by customers in Germany?
           select Products.ProductName from Orders INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID INNER JOIN OrderDetails on Orders.OrderID =                         OrderDetails.OrderID INNER JOIN Products ON OrderDetails.ProductID = Products.ProductID WHERE Customers.Country = 'Germany' GROUP BY Products.ProductName ORDER BY              count(Products.ProductName) desc;
           
           Gorgonzola Telino



 
