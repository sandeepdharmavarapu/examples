This is an attempt to solve Kaggle's [Bank Marketing UCI](https://www.kaggle.com/c/bank-marketing-uci) competition using H2O.ai. Final model can be tested from below showcase URL

**Showcase URL :** https://showcase.clouderizer.com/userserving/59619-81909d22-ebe0-442a-a1cb-986bd06b9726-SH/

### File Details

#### bank.csv

Bank Marketing UCI dataset available from [here](https://archive.ics.uci.edu/ml/datasets/Bank+Marketing)

#### Bank Marketing.flow

H2O.ai flow notebook which loads above dataset, parses it, builds an XGBoost prediction model.

#### bank_marketing_h2o_mojo.zip

XGBoost MOJO model built using default options in H2O.ai. This model can be used as it is for making predictions.

### Building the model

H2O.ai (with Flow UI) is the only pre-requisite to run this notebook. Any linux environment with around 4 GB RAM should be sufficient to run this. Linux docker containers are also fine. Instructions to install H2O.ai can be found [here](http://h2o-release.s3.amazonaws.com/h2o/rel-zahradnik/5/index.html)

This project was built using [Clouderizer Workspace](https://clouderizer.com/work-space). It helps to setup the dockerised environment for this project (including installing H2O.ai) on any local machine (Mac or Ubuntu) or on Cloud (AWS or GCP).
* Login to [Clouderizer](https://showcase.clouderizer.com)
* Go to Workspace tab and create a new project
* For **Code**, enter the git URL for this project
https://github.com/clouderizer/examples.git
* Leave **Data** blank. Under **Set up** -> **Remote Access**, enable H2O.ai option.
* Press finish to create the project.
* Run the project (locally or on cloud)
* Access H2O Flow UI console. Upload the 'Bank Marketing.Flow' notebook.
* Run all cells. This should load the dataset, parse it and build the XGBoost model.

### Deploying the model

H2O.ai offers us to build the model in MOJO format. This is a Java binary format. One of the ways to deploy this model for predictions and scoring is using [Clouderizer Showcase](https://clouderizer.com). It allows us to deploy the ML model in a containerized environment, setting up a RESTful server and a modern web application for scoring, without needing to write a single line of code. We can deploy this locally (any Mac or Ubuntu) or on Cloud (AWS or GCP).
* Login to [Clouderizer](https://showcase.clouderizer.com)
* Go to Showcase tab and create a new project
* Select H2O AutoML as project type and drag and drop the MOJO file from this repositary.
* Deploy the project (locally or on cloud)

Once deployed, you can get the model server URL. This URL can be used to call REST endpoints to make predictions. Or just open this URL in a browser to access auto generated Scoring UI.

**Demo Showcase URL :** https://showcase.clouderizer.com/userserving/59619-81909d22-ebe0-442a-a1cb-986bd06b9726-SH/

More details about Showcase customizations and options can be found [here](https://docs.clouderizer.com/showcase/introduction/)
