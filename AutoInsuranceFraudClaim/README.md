This is an implementation of a Kaggle' based notebook [Auto Insurance Fraud Detection](https://www.kaggle.com/buntyshah/auto-insurance-claims-data) competition using H2O. We use XGBoost algorithm with H2oAutoML module in python. Output performance can be greatly improved by careful selection of features. Intention of this example is to demonstrate the end to end workflow of building the model using H2O.ai and deploying it. Final model can be tested from below demo showcase URL

**Showcase URL :** [url here]

#### auto_insurance_h2o.zip

XGBoost MOJO model built using python H2o module [H2oAutoML](https://docs.h2o.ai/h2o/latest-stable/h2o-docs/downloading.html).

### Building the model
The auto-insurance-claims-using-h2o.ipynb has the installation requirements. Running that notebook will give a zip file which is a H2o based Clouderizer compatible format.

This project was built using [Clouderizer Workspace](https://clouderizer.com/work-space). It helps to setup the dockerised environment for this project (including installing H2O.ai) on any local machine (Mac or Ubuntu) or on Cloud (AWS or GCP).
* Login to [Clouderizer](https://showcase.clouderizer.com)
* Go to Workspace tab and create a new project
* For **Code**, enter the git URL for this project
https://github.com/clouderizer/examples.git
* Press finish to create the project.
* Run the project (locally or on cloud)
* Run all cells in the notebook. This should load the dataset, parse it and build the XGBoost model.

### Deploying the model

H2O.ai offers us to build the model in MOJO format. This is a Java binary format. One of the ways to deploy this model for predictions and scoring is using [Clouderizer Showcase](https://clouderizer.com). It allows us to deploy the ML model in a containerized environment, setting up a RESTful server and a modern web application for scoring, without needing to write a single line of code. We can deploy this locally (any Mac or Ubuntu) or on Cloud (AWS or GCP).
* Login to [Clouderizer](https://showcase.clouderizer.com)
* Go to Showcase tab and create a new project
* Select H2O AutoML as project type and drag and drop the MOJO file from this repositary.
* Deploy the project (locally or on cloud)

Once deployed, you can get the model server URL. This URL can be used to call REST endpoints to make predictions. Or just open this URL in a browser to access auto generated Scoring UI.

**Demo Showcase URL :** [url here]

More details about Showcase customizations and options can be found [here](https://docs.clouderizer.com/showcase/introduction/)

