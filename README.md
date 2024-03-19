# Data-Science-Model-Tuning-Project-ReneWind

**Business Context**

Renewable energy sources play an increasingly important role in the global energy mix, as the effort to reduce the environmental impact of energy production increases.

Out of all the renewable energy alternatives, wind energy is one of the most developed technologies worldwide. The U.S Department of Energy has put together a guide to achieving operational efficiency using predictive maintenance practices.

Predictive maintenance uses sensor information and analysis methods to measure and predict degradation and future component capability. The idea behind predictive maintenance is that failure patterns are predictable and if component failure can be predicted accurately and the component is replaced before it fails, the costs of operation and maintenance will be much lower.

The sensors fitted across different machines involved in the process of energy generation collect data related to various environmental factors (temperature, humidity, wind speed, etc.) and additional features related to various parts of the wind turbine (gearbox, tower, blades, break, etc.).

**Objective**

“ReneWind” is a company working on improving the machinery/processes involved in the production of wind energy using machine learning and has collected data of generator failure of wind turbines using sensors. They have shared a ciphered version of the data, as the data collected through sensors is confidential (the type of data collected varies with companies). Data has 40 predictors, 20000 observations in the training set and 5000 in the test set.

The objective is to build various classification models, tune them, and find the best one that will help identify failures so that the generators could be repaired before failing/breaking to reduce the overall maintenance cost. The nature of predictions made by the classification model will translate as follows:

True positives (TP) are failures correctly predicted by the model. These will result in repairing costs.
False negatives (FN) are real failures where there is no detection by the model. These will result in replacement costs.
False positives (FP) are detections where there is no failure. These will result in inspection costs.
It is given that the cost of repairing a generator is much less than the cost of replacing it, and the cost of inspection is less than the cost of repair.

“1” in the target variables should be considered as “failure” and “0” represents “No failure”.

**Data Description**

The data provided is a transformed version of original data which was collected using sensors.
Train.csv - To be used for training and tuning of models.
Test.csv - To be used only for testing the performance of the final best model.
Both the datasets consist of 40 predictor variables and 1 target variable

**Business Insights and Conclusions**

The predictors V36 takes the highest priority in predicting the component failures of the generators followed by V16, V26 and V14 takes the second, third and fourth priority by the XGBoost classifier algorithm.

The Predictors V7, V15 and V16 seem to have a slightly high positive correlation with the 'Target' variable. The Predictors V3, V18, V36 and V38 have a slightly high negative correlation with the 'Target' variable.

None of the Predictors seem to have a very high correlation with the 'Target' variable.

The algorithms performing and generalizing well on the Oversampled data are GBM, AdaBoost, Logistic regression and XGBoost.

The algorithms peforming and generalizing well on the undersampled data are Random Forest, GBM and XGBoost classifier.

The performance metrics of XGBoost classifier tuned with oversampled data on the test dataset is generalised with the validation set results. The recall score of the XGBoost classifier tuned model in the test set/Production dataset is 0.86 which is really good as it significantly reduces the number of False Negatives thereby making sure of predicting the generator failures of the wind turbine more efficiently.

The ReneWind company can implement the XGBoost classifier tuned model which is optimizing the recall score significantly so that predictive maintenance can be done efficiently as the failure patterns can be predicted much accurately and the component is replaced before it fails which will reduce the costs of operation and maintenance.
