# Investigating the relationship between discounts and order quantity.

This notebook investigates the relationship between discounts and order quantity in the Northwind database (created by Microsoft).

The null hypothesis is that discounts have no impact on order quantity.

⍺ = 0.05

The data is retrieved by submitting a query to an SQLite database.

The Quantity and Discount variables are the focus of this notebook. To create a far more normally distributed Series, the Quantity variable is transformed using the numpy.log1p (natural logarithm) function.

Several rows with uncommon discount levels are removed from the dataset. The fact that there were fewer than 5 orders placed with those discount levels led me to believe that there could be something different about those orders. Why would less than 5 orders have been made at a certain discount level? It doesn't seem like the business was offering those discount levels widely.

A t-test using the scipy.stats.ttest_ind function indicates that there is far more variation between  discounted and non-discounted orders than variation within those groups. There is an extremely low probability (far lower than the alpha value selected) that this variation would exist if the null hypothesis was true. We can therefore reject the null hypothesis in this case and say that discounts impact order quantity.

![image](https://user-images.githubusercontent.com/79678028/109748310-e5c26d00-7b95-11eb-846c-0dc2e5e808c7.png)




