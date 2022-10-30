# Multivariate-Time-Series-Forecasting-SalesData


Overview :

Mutistep-Mutlivariate Time series forecasting. Different datasets were combined by building relationships using Power bi. Data Analysis and visualization was done using Power Bi. Finally a dataset was formed using the important features. The Data cleaning and pre-processing was performed. Dataset had some important categorical features with many unique values that can contribute towards the accuracy of the model. So they were binary encoded using the category encoders library. A custom data generator function is used to create training data with past sales data’s independent variables and future sales . Finally the data is fit on a sequential model with stack containing a combination of Conv1D and LSTM layers. The trained model was then saved and encoders were pickled as part of the preparation for deployment. Model was deployed on azure cloud using AzureMl SDK.

Dataset Source :

Kaggle Competition Dataset

Libraries Used :

Keras, Tensorflow, sklearn,pandas ,numpy, category_encoder, Azureml etc 

Project Flow:

1)Data Preparation:

Combining data by building relationships between the tables in Power BI -> Data analysis on data -> Reports and Dashboards Preparation -> Preparing a final dataset with important features 

2)Training and Evaluation:

Importing the combined dataset - > Data is cleaned -> Categorical variables are binary encoded -> Preparing sets of past sales data as inputs and future sales data as targets using a custom data-generator function -> Splitting train and test data -> Model Training 

3)Deployment :

Saving best model and pickling encoders -> Registering Model to Workspace -> Creating and registering an environment with all the required dependencies -> Creating and registering AKS inference cluster -> Preparing an entry script -> Deploying the model on the cluster with appropriate inference and deployment configuration

Model Architecture :

Intuition behind using stack of LSTM layers on 

Stack of Conv1D layers – These are used to create feature of maps of a longer sequence , but they lack time sensitivity .

Stack of LSTM layers – The time sensitivity is taken care by these LSTM layers .

The sequences were very long as , even a single day had about 1700 plus steps , to predict on sales atleast based on past 3 or 4 days would sum the time steps to over 5100 steps. The loss explodes when we train the model and does not seem to converge which is logical .
But this project helped in understanding the use of a combination of  LSTMs and Conv1D’s to deal with longer sequence and forecasting. This also helped preparing a trained model for forecasting deployment into a cloud service.



