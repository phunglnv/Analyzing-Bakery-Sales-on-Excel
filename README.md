
# Should the bakery change menu?

This is the project to prace analyzing skills on Excel, follow the course Error and Uncertainty in Spreadsheets on Datacamp. 




## Scenario
Risky Business Bakery need of some help. They work hard, and their profits are declining. They look back through their sales data to determine how they can increase sales without significantly increasing costs.


## Dataset
Sales data from the Risky Business Bakery to answer question “Whether changing our prices will significantly affect demand and increase our sales”. 

The dataset contains the following columns or variables: 

- Transaction ID is the order number in the point-of-sale system
- The "Day" column refers to the day of the week on which the sale occurred
- The "Date" and "Time" columns indicate when the item or items were sold
- "Item" refers to the food or beverages the customer purchased
- And "Price" is how much they paid for it

In this project, I will analyze data based on dates and times. For example, the restaurant manager might want to know what time of day our bakery is the busiest to see how we might increase our sales. 

In Excel, data that are stored as times range from 0 to 1 (0 corresponding to midnight and 1 corresponding to the last second of the day). Each time can be stored as a decimal between 0 and 1, for example, 11:04 and 6 seconds (in the morning), corresponds to around 0.46, and noon corresponds to exactly 0.5, which makes sense if we think of a day being represented by 1.

![1](https://user-images.githubusercontent.com/105278875/205305702-b2a621be-ab95-4c91-8661-16a88a181605.PNG)
## Functions
- SUMIF(): allows to add up cell ranges if cells meet certain conditions, sorting like filtering data.
- UNIQUE() and SORT() to get a list of the unique values in a given range, and also to extract the days of the week, or the list of items that were sold during a given period.
- Finally, I will calculate percentages to see what proportions of our sales come on different days or for different items.
- FILTER() function takes a range and one or more conditions to use to filter that range.
- DATE() function takes a given year, month, and day and converts them into a date value.
- Standard deviation measures how much variation exists in the data. More specifically, it indicates how much a given value varies (or deviates) from the average value for the dataset.
- MAXIFS() function takes the range of cells within which to find the maximum value, the range of cells to apply the criterion, and the criterion to apply.
- CORREL() function takes two ranges of cells to correlate and returns a correlation coefficient. These coefficients vary between -1 and 1 and can have a negative or positive relationship.
- To add noise or variation to our data to model results under different conditions, use RANDBETWEEN()
- SPARKLINE() are graphical representations of data in a single cell


## Which items sell best and which days are busiest?

![2](https://user-images.githubusercontent.com/105278875/205305779-53bfaff5-5985-471c-b6ed-ec06afa11c28.PNG)

1. Add the list of total sales for each day by using SUMIF function. 
2. Use combination of SORT and UNIQUE to generate a sorted list of unique bakery items. 
3. Calculate the total sales for each item. 
4. Calculate the percentage of total sales for each item. 

From the result, we see that Saturday is the busiest day of the week and Coffee is best-seller of this bakery. 



## Falling on hearth times

The Risky Business Bakery is also want know if most of their sales come in the morning or afternoon to schedule their employees appropriately.

In this case, I applied SUMIFS instead of SUMIF. 

The SUMIF formula returns the sum of cells based on one criterion (a result that matches one condition). Whereas, the SUMIFS function returns the sum of cells that meet multiple criteria. 

1. Add up the sales that occurred before noon for each day (2 criteria: the day and the time)
2. Totally the sales that occurred at or after 12 PM for each day. 

We can easily see that most of the sales come from after 12PM most days of the week.

![3](https://user-images.githubusercontent.com/105278875/205306032-e3fb956b-62bb-4dd6-843a-e52766710a0e.PNG)


## Changing prices 
In an effort to increase demand and grow bakery’s sales, they made some pricing changes starting on 2/21/2017. In an effort to draw more people at lunch, they decreased prices by 20% on lunch items (i.e., soup, sandwiches, and chicken stew) but increased prices on drinks by 20% to offset the lower revenue. They also decreased all other prices by 10% in an effort to boost demand.

1. I start by filtering the data into two groups to perform other analyses (before and after 2/21/2017). 
2. To determine whether changing prices improved total sales, I will do the T-TEST, which  indicates whether there are statistically significant differences between two groups of data. In this case, I applied value of 2 to determine whether the average item sale price differed significantly before and after the price change.


![5](https://user-images.githubusercontent.com/105278875/205306571-b4281dd6-4bbe-44c0-8591-07ced2946b3d.PNG)

We can see from the result that 

- Prices varied more **before**  we updated them, which we can tell from the higher standard deviation.
- Sales were significantly higher before prices changed.
## Does the rain affect?
Before assuming that our pricing changes didn't work (or even worked in the opposite direction), I might want to conduct some additional analyses. After all, there might have been other factors that affected sales in those weeks.

On the dataset, we have a column that shows the number of inches of rain that fell that day. This is the total for the entire day, not just for the time at which the sale happened (which wouldn't be useful because rain doesn't accumulate immediately). If we calculated the sum of this column, we would be counting the daily total once for each transaction, which would inflate our totals.

1. Create a list of unique dates.
2. Calculate the maximum number of inches of rain for the corresponding day. 
3. Calculate the total sales for the corresponding day. 

To determine whether rain was a factor in customers' purchasing habits, first determining whether it rained more before or after they changed their pricing structure. It can also correlate total rainfall with total sales to see how the two are related.

![6](https://user-images.githubusercontent.com/105278875/205306775-5b4b8ea9-55ee-497d-b7e9-b0bb6c8b9595.PNG)


## Are we certain now?
The analysis suggests the weather didn't cause the drop in sales either, but there might have been other outside factors that influenced sales. As we reviewed, we can add random variation to your data to model different circumstances. 

1. Generate a random number between 0 and 2. 
2. Use the random number you generated to compute the new sale amount.
3. Calculate sales before and after changing prices. 
4. Create sparklines for each of three sum (pre, post and random variation). 
5. Make a quick comparisons between groups of data. 

The values from  `T.TEST()`  indicate that there were significant differences between before and after prices changed (t < 0.05) but not between estimated values and the actual sales after changing prices (t > 0.05).

![7](https://user-images.githubusercontent.com/105278875/205307001-5f573c34-73b5-473c-97a6-83b09fc90b79.PNG)

![8](https://user-images.githubusercontent.com/105278875/205307091-7b38cc70-2fd8-4851-a89c-91dc64cfd695.PNG)


## Conclusion
1. Sales tend to be highest on the weekends.
2. The bakery's largest source of revenue comes from coffee sales.
3. Sales were significantly higher before prices changed.
4. The rainy weather didn't cause the drop in sales, there might be other factors. 