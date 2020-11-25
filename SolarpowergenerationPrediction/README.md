
This is a demonstration of the end to end workflow of building the model and deploying it. I have chosen ‘heart failure prediction’ dataset from kaggle for this purpose.

Solar power prediction dataset available from [here](https://www.kaggle.com/andrewmvd/heart-failure-clinical-data)

### File Details

#### solarpowergeneration.ipynb

This is the notebook that loads above dataset, analysis it and builds models using Random Forest, LGBM, SVM, Decision Tree and Gradient Boosting classifiers.

### Building the model

* I chose “Solar Power Generation data” from kaggle(https://www.kaggle.com/anikannal/solar-power-generation-data) to build my model.
* The task of this project is to predict the solar power generation for the next couple of days.
* The data I had in hand needed some modification to fit my algorithm. I grouped the rows on timestamp and removed all columns except for DAILY_YIELD because we only need to predict DAILY_YIELD.
* Any time series data needs to be checked for stationarity to build a model out of it. I have performed Dickey–Fuller test for stationarity and the p-value I got from it is 0.17(A p-value > 0.05 makes the data non stationary).
* I used Auto Arima that makes the data stationary and fits the best ARIMA model. It seeks to identify the most optimal parameters for an ARIMA model, settling on a single fitted ARIMA model.
* Use python's pickle to package the model and download the model file.
* We have successfully built our model and packaged. But we are not done yet. Here comes the part which is the prime focus of this article i.e Model deployment.

### Deploying the model

One of the ways to deploy this model for predictions and scoring is using [Clouderizer Showcase](https://clouderizer.com). It allows us to deploy the ML model in a containerized environment, setting up a RESTful server and a modern web application for scoring, without needing to write a single line of code. We can deploy this locally (any Mac or Ubuntu) or on Cloud (AWS or GCP).
* Login to [Clouderizer](https://showcase.clouderizer.com)
* Go to Showcase tab and create a new project
* Select Python Pickle as project type and drag and drop the pickle file we generated in our model building part.
* Deploy the project (locally or on cloud)

Once deployed, you can get the model server URL. This URL can be used to call REST endpoints to make predictions. Or just open this URL in a browser to access auto generated Scoring UI. 

The best part is you can view various stats, error metrics for the predictions made by your users on your Analytics dashboard. Also you can download the entire stats data as csv. You can upload the real values of your time series to calculate error metrics with the help of all the predicted values.

You can also retrain your model by setting out your existing training API endpoint. You will have options to automate the deployment with your retrained model once retraining is done or to do it manually with zero downtime. You can also configure to retrain your model when the error metric surpasses the set threshold. 
