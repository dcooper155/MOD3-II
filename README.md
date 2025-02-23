# This program predicts hospital length of stay using a Random Forest Regression model
# Modules 
- test_train_split is a cool feature (module) of this library (sklearn). It splits the data into training and testing--usually an 80/20 split.
# The model: Random Forest Regression
- I'm familiar with what I've done in class - L1/L2 regressions. But I use random forests on Dataiku when dealing with non-linear regressions. I pulled this code from a book I frequently use: Machine Learning with PyTorch and Scikit_Learn, which offers links to great tutorials.
OneHotEncoder and StandardScaler: I'm not all that familiar with these modules inside sklearn. I pulled them from the same book I mentioned above. OneHotEncoding takes all of our categorical variables (e.g., doctors' names) and converts them into binary numbers and places each in a new category. Moreover, it ignores unknowns, like if we put a doctor's name in that it doesn't recognize--it will just ignore it. 'cat' (for category) was the label used in the book, so I stuck with it--cut and pasted, essentially.
- StandardScaler: in the same "pre-processing" vein that sklearn does for us, StandardScaler transforms number columns ('num') to binary numbers as well, where 0 is the mean and 1 is the standard deviation. Basically, when numbers/integers are scaled like this, they all contribute evenly to the model. ColumnTransformer, then, is the function we call to pre-process categorical variables and numbers. It's pretty cool, actually.
# Outputs
- Mean Absolute Error gives us the absolute difference between actual length of stay and the predicted. This model's prediction is off by 1.24 days.
- Mean Squared Error gives us the average of the squared difference between actual and predicted. It essentially penalizes large errors because they are squared. With this method, the model is off by 3.43 days. We could improve these numbers, but it could get complicated. We could also drop some of the columns that don't matter, like doctors' names. But when I look at this data visually, it's good to see the docs' names, because it could give us some insight into which doctors have the longest LOS. I'm less concerned with accuracy than I am with building a workable model.
- R2 tells us how well the model explains variance in the target variable. The closer to 1, the better the model explains the variance. This model's R2 is .94, which is pretty good--the model fits the data. It explains 94% of the variance, essentially.
# Putting it all together
- Pipeline puts it all together for us. It pre-processes our data and then does the random forest regression on both training and test data. Very slick.
# Link to the model
https://github.com/bllarso2/CAS-502-LOS/blob/main/CAS502_FINAL_ST.ipynb
