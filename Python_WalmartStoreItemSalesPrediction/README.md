This is an attempt to solve Kaggle's [Walmart Store Sales Forecasting](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting/overview) recruiting challenge using python. We use Random Forest regression available out of the box in sklearn. Output performance can be greatly improved by careful selection of features. Intention of this example is to demonstrate the end to end workflow of building the model using python and deploying it.

### Building the model
This project was built using [Clouderizer Workspace](https://clouderizer.com/work-space). It helps to setup the dockerised environment for this project on any local machine (Mac or Ubuntu) or on Cloud (AWS or GCP).

* Login to [Clouderizer](https://showcase.clouderizer.com)
* Go to Workspace tab and create a new project
* For **Code**, enter the git URL for this project
https://github.com/clouderizer/examples.git
* Leave **Data** blank. Under **Set up** -> **PIP Packages**, Enter all the dependencies(find them in requirements.txt).
* Press finish to create the project.
* Run the project (locally or on cloud)
* Run all cells in .ipynb. This should load the dataset, parse it and build the Random Forest model.
* A walmart_item.joblib will be created. This file contains the trained model.

### Deploying the model

One of the ways to deploy this model for predictions and scoring is using [Clouderizer Showcase](https://clouderizer.com). It allows us to deploy the ML model in a containerized environment, setting up a RESTful server and a modern web application for scoring, without needing to write a single line of code. We can deploy this locally (any Mac or Ubuntu) or on Cloud (AWS or GCP).


* Login to [Clouderizer](https://showcase.clouderizer.com)
* Go to Showcase tab and create a new project
* Select python as project type and drag and drop the walmart_item.joblib file from this repositary.
* Deploy the project (locally or on cloud)

Once deployed, you can get the model server URL. This URL can be used to call REST endpoints to make predictions. Or just open this URL in a browser to access auto generated Scoring UI.

More details about Showcase customizations and options can be found [here](https://docs.clouderizer.com/showcase/introduction/)