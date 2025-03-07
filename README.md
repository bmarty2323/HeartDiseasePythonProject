# HeartDiseasePythonProject
EDA and Machine Learning with Heart Disease dataset

The World Health Organization estimates that 17.9 million people die from cardiovascular diseases (CVDs) every year.
There are multiple risk factors that could contribute to CVD, such as unhealthy diet, lack of physical activity, or mental illness. Identifying these risk factors early on could help prevent many premature deaths. In this project, I am expoloring these factors and creating a logistic regrerssion model to determine correlations and variables that could point to a higher likelihood of heart disease.
  
  The dataset includes relevant information for each patient, such as their personal information and some medical data, including whether or not they have had heart disease before. The pic below shows categorical info, and the dataset can be accessed from Kaggle here: https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction

![info](https://github.com/user-attachments/assets/70885e2b-0e65-4e62-913f-938c78378659)

![describe](https://github.com/user-attachments/assets/c78ab290-31fe-4e94-b3a4-d1bdcd94d8e8)


  After doing inital cleaning and EDA using graphs and other methods, the following observations can be made:
The dataset is highly skewed towards male patients. This could potentially induce a bias in the model and impact predictions for any female patients in unseen data. The target variable is somewhat evenly distributed, which is beneficial for training the model.
A significant number of patients, 392, diagnosed with heart disease have asymptomatic (ASY) chest pain. While chest pain could be a relevant feature for the model, asymptomatic implies that those patients who had heart disease did not have chest pain as a symptom.
It also appears that Cholesterol has no correlation with heart disease, which is counter-intuitive.
  
  Looking at the data, it appears there are a number of rows in the "Cholesterol" and "RestingBP" categories with 0 values. This is likely due to error, and I have decided to remove these rows as opposed to other methods, such as assigning the 0 values a median category score.

![box_plots](https://github.com/user-attachments/assets/c774b02a-5d6f-4a19-83b7-55b7d5c96d2e)

![histplot](https://github.com/user-attachments/assets/698e01cd-bafe-4dcc-98fc-955778c40024)


  In order to prepare the data for regression analysis, dummy variables need to be created for the categorical variables. This allows for further analysis based on correlations between the dependent variable and other variables. In looking at the heatmap and other metrics, a coefficient threshold of 0.3 was chosen. Next in the process is to separate the dependent and independent variables, and to split the model into test and training sets. Once complete, I will set the parameters and run the logistic regression and fit the model.
  
  Now that the model has been created and fit, the dependent variable needs to be predicted based on the results. To view the predictive results, I create a Confusion Matrix. This matrix displays accuracy information about the model, to compare expected results with actual results. From the matrix shown below, you can see the model had 69 True Positives vs 13 False Positives. Additionally, 85 True Negatives vs 17 False Negatives. To add insight to the Confusion Matrix, I produced a classification report. The table below shows the accuracy scores from the model. The f1 score is a good indicator of model performance. Although the model has an accuracy of over 80%, the results indicate that the model is a better predictor of whether a person does not have heart disease than if they do. 

![scores1](https://github.com/user-attachments/assets/a6b58753-51ff-4b68-bd40-a1a2d421d036)


![confusion_matrix](https://github.com/user-attachments/assets/d3980272-43a3-4d75-a19c-3679a02268d6)

In addition to logistic regression, I built a decision tree based model to better understand the model using cross validation (CV). For this, a Classifier was set, and CV parameters were determined. The cross validation is run, and the new model is fit. After the fit, I determine the best parameters, and best score predicted by the tree based model. The results determined that the accuracy score is right in line with the previous model, but the f1 score is slightly higher at 85. Creating a plot tree, I am able to visualize the highest performing results estimator and its criteria. Interpreting the chart below, it is clear to see that the variable that is most highly correlated with heart disease is a flat ST slope. Next would be the ChestPainType, followed by OldPeak and FastingBS.

![decision_tree](https://github.com/user-attachments/assets/3270dc9a-3dff-4ca6-9365-96bef90adbdf)

To conclude, while the model did perform well, with an 84% accuracy score, I believe improvements can be made. Perhaps a better score would be attained were other variables added, such as "ChestPainType_ATA", or "ST_SlopeDown". Although there were a higher number of males with heart disease compared to females, I purposely left this variable out of my model. Surely, the performance scores would be higher had I included gender. Though the models can be improved upon, they did appear to be good predictors of both those patients with heart disease, and those without.








  
