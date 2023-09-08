Overview

This project is about a person who wants to buy a house in King County, Washington. They want to live there for a few years and then sell the house for a profit. The buyer has a moderate income, wants to buy a home for less than $1 million, and has money set aside for repairs. The data on house purchases in the area is put into a Jupyter notebook, cleaned, changed, and modeled to show how the different parts of a house relate to each other. Linear regression is used to find the best way to guess the price of a house and to figure out how much each factor affects the price.

Business Problem

What are the effects of living in one part of King County instead of another?
Where is the best place to put money for repairs?
What's the link between the size of a house's living space and how much it costs to buy?

Data

The data for this project comes from the kc_house_data.csv file on Kaggle.com. It has 21,597 records for homes sold in King County, Washington, between 2014 and 2015. This information includes a house's living space in square feet, the number of bedrooms it has, and a grade based on how well it was built. The goal variable is the "price" column.

Methods

When cleaning up the data for the first time, you had to get rid of copies and extreme outliers, give missing data values, and change columns to the right data types. The principles of linear regression are not met by the model that was trained here. So, all category factors are turned into indicator columns. Some (months, bedrooms, etc.) are first binned to lower the number of features. Using user-made tools to split data based on how recently it was renovated and where it was, new models are made. Model two, which has also been trained up to this point, has a higher r-squared, but it still doesn't meet the conditions. For the third model, the outliers in the 'price' and'sqft_lot' columns were taken out by using the interquartile range. This model meets both the normality and homoscedasticity assumptions and gives an r-squared of 69.1. Lastly, for model 4, both continuous variables were log transformed and scaled to make features that were more evenly spread out. This model meets all four assumptions of linear regression, so its r-squared value of 68.6% is a lot more accurate.

Results: 

Model 4's factors give a lot of information about what to look for in a home and what, if any, changes should be made to boost its selling value.

Coefficients for Model 4

When the quality of building was made better, the price of Grade_High_Quality and Grade_Above_Average houses went up by $254K and $97K, respectively, compared to the price of houses of average grade. It has also been shown that the state of a home has a good effect on its price, with the best condition adding about $161k to the price compared to the worst condition. When the number of beds goes up, the price goes down, according to our bedroom factors. This doesn't make sense and needs to be looked into more.

Conclusions

Analysis shows that Sections 1 and 2 have the most positive effect on the price. Model 4 shows a link between the quality of work and the price of a home, so owners should think about spending more on high-quality construction and building materials. Last but not least, the model shows that for every

What's Next?

Using geographic libraries, more research could include making features based on where they are, like how close they are to schools or public places. Other possible next steps could include adding more data sets with information about nearby jobs, public transportation, etc.