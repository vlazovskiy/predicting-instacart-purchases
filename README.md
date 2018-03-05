**Topic:** Predicting Whether a Product Will Be in Instacart Users' Next Order

**Presentation.** Presentation can be found [here](https://github.com/vlazovskiy/sf18_ds9/blob/master/student_submissions/projects/mcnulty/lazovskiy_vladimir/Predicting_customer_orders_with_instacart.pdf).

**EDA.** Some EDA Tableau visuzliations can be found [here](https://github.com/vlazovskiy/sf18_ds9/blob/master/student_submissions/projects/mcnulty/lazovskiy_vladimir/EDA%20with%20Tableau.md).

**Project goal.** The goal of my project is to predict whether a customer will reoder a certain product. Essentially, this a classification problem with two classes: 1 if a user reorders a product and 0 otherwise. The data set was taken from [Kaggle](https://kaggle.com/c/instacart-market-basket-analysis/data), and the preliminary model relies on the baseline work taken from [here](https://github.com/JEddy92/Metis-Project3-InstacartKaggle).

**Data and Features.** As mentioned before, the data was taken from Kaggle, and some initial features from JEddy92's notebook were considered for modeling. After that, I engineered 13 new features: average day of week when product ordered, average day of the week the product was ordered, average days since prior order, average hour of the day when a certain user orders a product, and several others. I also expanded department names into feature columns.

**Models.** After doing a wuick run with KNN, Naïve Bayes, Logistic Regression, Random Forest and XGBoost, I selected Logistic Regression and XgBoost for further investigation and ultimately stopped on Logistic Regression because it was easier to tune and understand. I scaled features using MinMaxScaler, and finally addressed class imbalance by assigning a weight multiplier to the minority class. 

**Results.** I evaluated my model on its F1 score because both precision and recall were important for my prediction: I wanted to make sure users do order every predicted product by having higher precision and to make sure that there is always product available by having higher recall. My metrics for the holdout test set were the following: F1 = 0.3928, Precision = 0.3, Recall = 0.5. Interestingly enough, the features that impacted the odds of the product being reordered were the following: frequency (25%), user total orders (16%), product total orders (8%), product's add to cart order (-10%), user's product totals average global average (-7%). 
