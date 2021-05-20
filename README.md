SECTION: Guiding questions:


Problem Statement:

How close can we get to predicting the final sale price of a house in the Ames data set?

What features are most important in predicting sale price of a house in the Ames data set?

How is neighborhood associated with final sale price of a house in the Ames data set? 


SECTION: Background

In this project I am using Aimes housing data to predict sales prices of homes in Aimes, Iowa. I received information on 81 features, including sale price, about 2,051 homes in Aimes, Iowa. I created models on this data and used my model to make sale price predictions for houses where I know all the same features except Sale Price. In this project I made 4 different models, one of which is interactive and fully adjustable in realtime. My root mean squared error so far on my top model's predictions, when applied to unseen data, is 23082.1507 dollars. This shows that the average magnitude of error on sale price for my best model so far is 23082.1507 dollars. 


```python
SECTION: Methods
```

1. Find null values in numerical columns and replace with the mean value from that column
2. Find all column names data type object
3. Dummify all columns with data type object
4. Sort features so that training data has the same features as testing data. Also include Sale Price in testing data
5. Set X variable as all columns except Sale Price. Set y variable as Sale Price.
6. Run train test split, call linear regression and then fit training data to linear regression 
7. Check R2 scores, cross valuation scores and most importantly RMSE!
8. Now reiterate the model and try to improve scores R2 scores, cross valuation scores and most importantly RMSE
9. For the new model, scale the data with a standard scalar, run a regression to find a strong  alpha value, and now fit your model with the lasso 
10. Check scoring metrics again and then reiterate the model
11. Write a function to sort the lowest absolute value of scaled coefficients for all features
12. Drop all features with the smallest coefficients (drop coefficients with values between -3000 and 3000)
13. Assign my new feature engineered data to an X value and then fit with polynomial features
14. Check that the shape of your x with polynomial features is shape (w, z) where w>z 
15. Fit new X and y to a linear regression
16. Check scoring metrics again (most importantly RMSE)
17. In order to deal with an overfit model, scale the data with a standard scalar, run a regression to find a strong alpha value, and now fit the model with a lasso function
18. Reiterate on step 12 and rerun the notebook to find the best features to drop and continue RMSE improving score
19. Reiterate on your alpha value search in step 17 to continue to improve the alpha value and improve RMSE score


```python
CONCLUSIONS AND BREAKDOWN OF CORE IDEAS:
```

As an answer to our first guiding question, my root mean squared error on this model's predictions (so far), when applied to unseen data, is 23,082.1507 dollars. This means that we can expect my model to predict price fairly accurate within 23,082.1507 dollars of a properties actual Sale Price. 

Below are each of the top 10 correlated features to sale price and their corresponding coefficients from my linear model. This is helpful for showing how much a homeowner or real-estate investor can increase the value of a home by investing in the following feature upgrades. The coefficients are interpreted below. 

****

Each extra unit of Overall Qual, all else being equal, leads to an increase of Sale Price of 6882.710389

Each extra unit of Year Built, all else being equal, leads to an increase of Sale Price of 174.325393 dollars

Each extra unit of Year Remod/Add, all else being equal, leads to an increase of Sale Price of 44.067666 dollars

Each extra unit of Total Bsmt SF, all else being equal, leads to an increase of Sale Price of 7.641452 dollars

Each extra unit of 1st Flr SF, all else being equal, leads to an increase of Sale Price of 11.502933 dollars

Each extra unit of Gr Liv Area, all else being equal, leads to an increase of Sale Price of 27.246149 dollars

Each extra unit of Garage Cars, all else being equal, leads to an increase of Sale Price of 8619.707201 dollars

Each extra unit of Garage Area, all else being equal, leads to an increase of Sale Price of 2.650013 dollars

Each extra unit of Exter Qual_TA, all else being equal, leads to an increase of Sale Price of -32375.395191 dollars

Each extra unit of Kitchen Qual_TA, all else being equal, leads to an increase of Sale Price of -26282.449721 dollars

****

Furthermore predictions of sale price by my model can be used to figure out if a home is being sold above or below market value. For example, if a home is found on the market that is listed significantly below the predicted sale sale price, this home is likely a great value purchase. Conversely, if a home is listed significantly above the predicted sale value, this home is likely above market value. In this way, the model can help individuals make smarter and more informed home purchases. Additionally, this model can help homeowners learn what is an appropriate value to list as the sale price of their home. 

Finally, I used my original linear model to find the following coeficients for neighboorhood and its corelation to sale price.  This list tells you which neighboorhoods have a possitive and negative correlation to sale price as predicted by my model. The interpretation of these coeficients is that, all else being equal, being in the neighborhood will raise or lower the sale price of the home by the dollar value of the associeted Coefficient. 

****

Neighborhood Name	Coefficient Value

Neighborhood_StoneBr	 |             33091.187974

Neighborhood_NridgHt	   |           21509.021303

Neighborhood_NoRidge	  |            17750.146644

Neighborhood_Somerst	    |          -1132.742310

Neighborhood_NPkVill	     |         -4191.973771

Neighborhood_Greens	         |         -6495.283524

Neighborhood_BrDale	         |        -7233.413614

Neighborhood_Veenker	     |        -9033.538074

Neighborhood_Crawfor	      |        -14190.583482

Neighborhood_Timber	          |        -23557.201438

Neighborhood_Blueste	       |       -23613.409059

Neighborhood_SawyerW	       |       -23759.311360

Neighborhood_Gilbert	       |       -23859.888164

Neighborhood_MeadowV	       |       -24798.064956

Neighborhood_ClearCr	        |      -25467.362571

Neighborhood_CollgCr	         |     -25477.644798

Neighborhood_NWAmes	              |    -26214.152334

Neighborhood_NAmes	               |   -28086.176463

Neighborhood_BrkSide	            |  -28643.230386

Neighborhood_Mitchel	     |         -29079.413927

Neighborhood_Sawyer	          |        -30149.989479

Neighborhood_IDOTRR	           |       -33977.940798

Neighborhood_SWISU	            |      -34907.252093

Neighborhood_OldTown	         |     -35063.578194

Neighborhood_Edwards	          |    -42558.069846

****




