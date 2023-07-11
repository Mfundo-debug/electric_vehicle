# Electrical Vehicle Data (1997-2024)

## Project Description

-   This dataset shows the Battery Electric Vehicles (BEVs) and Plug-in Hybrid Electric Vehicles (PHEVs) that are currently registered through the Washington State Department of Licensing (DOL) the source of the dataset is shared by the Us government below are the features of the dataset which are important to understand before working with the data.

### Dataset information

-   [x] model year-\> in which year the car is launched or it will be launched.

-   [x] Make -\> manufacturing company name

-   [x] Model --\> Car Model Name

-   [x] Electric vehicle type --\> type of electric vehicle(Battery Electric Vehicle or Plug-in Hybrid Electric Vehicle )

-   [x] CAFV --\> refers to vehicles that qualify for certain incentives, benefits, or programs based on their use of clean or alternative fuels.

-   [x] Electric Range --\> The term "electric range" refers to the distance or the maximum range that an electric vehicle (EV) can travel on a fully charged battery before it needs to be recharged. It represents the total driving distance an EV can cover solely using the energy stored in its battery pack.

-   [x] Base MSRP (\$)--\>(Suggested price by Manufacturer it is a base price dealer have the freedom to change the price as desired ) It refers to the starting price set by the manufacturer for a particular vehicle model without any additional options, upgrades, or accessories.

-   [x] (DOL)The Department of Licensing--\> is a state agency in the United States that is responsible for various driver and vehicle-related services in the state of Washington. The DOL oversees the issuance and renewal of driver's licenses, identification cards, and vehicle registrations.

-   [x] Electric Utility --\>Electric utilities are responsible for providing the necessary infrastructure to supply electricity to EV owners, including charging stations, grid connections, and electricity distribution networks.

# Steps

-   [x] Data Cleaning
-   [x] Data Analysis, Visualization and exploration for US Elelctrical cars
-   [x] Data Modelling
-   [x] Evaluation of the xgboost model
-   [x] Checked the model convergence
-   [x] Checked the model performance on test data
-   [x] Checked the model performance on train data

```{python}
# plot the learning curve
from sklearn.model_selection import learning_curve
train_sizes, train_scores, test_scores = learning_curve(xgb_model, X_train, y_train, cv=5, scoring='neg_mean_squared_error', n_jobs=-1, train_sizes=np.linspace(0.01, 1.0, 50), verbose=1)
plt.plot(train_sizes, -test_scores.mean(1), 'o-', color="r", label="Test score")
plt.plot(train_sizes, -train_scores.mean(1), 'o-', color="g", label="Train score")
plt.xlabel("Train size")
plt.ylabel("Mean Squared Error")
plt.title('Learning curves')
plt.legend(loc="best")
plt.show()
```

```         
[learning_curve] Training set sizes: [  860  2599  4338  6077  7815  9554 11293 13032 14771 16510 18248 19987
 21726 23465 25204 26942 28681 30420 32159 33898 35637 37375 39114 40853
 42592 44331 46070 47808 49547 51286 53025 54764 56502 58241 59980 61719
 63458 65197 66935 68674 70413 72152 73891 75630 77368 79107 80846 82585
 84324 86063]
[Parallel(n_jobs=-1)]: Using backend LokyBackend with 16 concurrent workers.
```