
This is a demonstration of the end to end workflow of building the model and deploying it. I have chosen ‘heart failure prediction’ dataset from kaggle for this purpose. Final model can be tested from below demo showcase URL.

Showcase URL : https://showcase.clouderizer.com/userserving/63749-a5e5497d-5fe7-4a37-b644-ef7ee877ee73-SH



Heart failure prediction dataset available from [here](https://www.kaggle.com/andrewmvd/heart-failure-clinical-data)

### File Details

#### heartfailureprediction.ipynb

This is the notebook that loads above dataset, analyses it and builds models using Random Forest, LGBM, SVM, Decision Tree and Gradient Boosting classifiers.

#### heartfailureprediction.pkl

Random Forest model stored in pickle. This model can be used as it is for making predictions.

### Building the model

* The dataset we have from kaggle looks clean to me, so no need for any data cleaning. 
* Let’s do our feature selection using correlation matrix. From the features available, I would want to see what input features are more relevant to our output and eliminate non relevant ones from the list so as to improve the performance of our model. 
* From the correlation matrix, I will pick the features having the correlation value in the range (<-0.2 and >0.2). Age, serum_creatinine, serum_sodium and ejection_fraction form our list of input features that are highly correlated to output feature DEATH_EVENT.
* I have tried out various classifiers out of which Random Forest gave the best accuracy. So, I am building my model with it.
* Use python's pickle to package the model and download the model file.
* We have successfully built our model and packaged. But we are not done yet. Here comes the part which is the prime focus of this article i.e Model deployment.

### Deploying the model

One of the ways to deploy this model for predictions and scoring is using [Clouderizer Showcase](https://clouderizer.com). It allows us to deploy the ML model in a containerized environment, setting up a RESTful server and a modern web application for scoring, without needing to write a single line of code. We can deploy this locally (any Mac or Ubuntu) or on Cloud (AWS or GCP).
* Login to [Clouderizer](https://showcase.clouderizer.com)
* Go to Showcase tab and create a new project
* Select Python Pickle as project type and drag and drop the pickle file from this repository.
* Deploy the project (locally or on cloud)

Once deployed, you can get the model server URL. This URL can be used to call REST endpoints to make predictions. Or just open this URL in a browser to access auto generated Scoring UI.

The best part is you can view various stats, error metrics for the predictions made by your users on your Analytics dashboard. Also you can download the entire stats data as csv.

You can also retrain your model by setting out your existing training API endpoint. You will have options to automate the deployment with your retrained model once retraining is done or to do it manually with zero downtime. You can also configure to retrain your model when the error metric surpasses the set threshold. 


