
# eT3-Database-Task

In this task, it's required to  Import the provided excel sheet into any relational database and answer certain questions using sql queries.
This task is submitted to eT3 - Internship 2022




## Installation

Install Any relational database, I used mysql workbench

```bash
https://dev.mysql.com/downloads/workbench/
```

Download the drinkMenu.csv dataset 

```bash
https://drive.google.com/file/d/1osclWvpXTtIBV4t0fTBuPux74RkIkwmX/view
```

       


## How to run MySQL workbench and import csv file
### open MySQL workbench and press on localhost
<img src="/Screenshots/How to Use/How_to_use1.png" width=70%>

### type your root password
<img src="/Screenshots/How to Use/How_to_use2.png" width=70%>

### create a schema with any name
<img src="/Screenshots/How to Use/how_to_use3.png" width=70%>

### right click on tables of schema to import csv file
<img src="/Screenshots/How to Use/how_to_use4.png" width=70%>

### locate the path of the file and import it.
<img src="/Screenshots/How to Use/How_to_use5.png" width=70%>


## Questions and Answers

1. Which drink has the highest calories from the dataset ?
```sql
SELECT Beverage,Calories as 'highest_calorie_drink'
FROM drink_menu.drink_menu_table
where Calories = (SELECT MAX(Calories) from drink_menu.drink_menu_table);

or

SELECT Beverage,Calories as 'highest_calories_drink'
FROM drink_menu.drink_menu_table 
ORDER BY Calories DESC
LIMIT 1


```


<img src="/Screenshots/Queries/First_Query_Method1.png" width=70%>
<img src="/Screenshots/Queries/First_Query_Method2.png" width=70%>


2. What is the average calorie amount for each drink category
 ```sql
SELECT Beverage_category , count(Beverage_category)
FROM drink_menu.drink_menu_table
GROUP BY Beverage_category
```
<img src="/Screenshots/Queries/Second_Query.png" width=70%>

3. Which drinks have below average calorie amount ?
 ```sql
SELECT Beverage as "Drinks below average value (201.04)",Calories
FROM drink_menu.drink_menu_table
where Calories < (select avg(calories) from drink_menu.drink_menu_table)
```
<img src="/Screenshots/Queries/Third_Query.png" width=70%>

