# Operationalizing Machine Learning

In this project, we work with the Bank Marketing dataset. The dataset contains information about the marketing campaign of a Portuguese Banking Institute. The classification goal is to predict whether a client will subscribe to a term deposit or not. We use Azure to configure a cloud-based machine learning production model, deploy it, and consume it. Atlast, we will also create, publish, and consume a pipeline.

## Architectural Diagram
////////////////////////0.architecture

## Key Steps

Key steps involved in this project are:
### Authentication:
   Using authentication with automation is the best way to go. If authentication is not enabled, human interaction will be required which will interrupt the       continuous flow of operations. Hence Continuous Integration and Delivery system (CI/CD) rely on uninterrupted flows.
   Types of Authentication: 1. Key based   2. Token based   3. Interactive 
### Dataset registeration
Create a new dataset by navigating in datasets section from the left panel of Azure studio. Dataset can be created either by using the web url or by uploading the data from local csv.

///////////////////////1.dataset

### AutoML Model:
This feature of Azure allows to build ML models with high scale, efficiency and productivity, all while sustaining model quality. Thus automating the time-consuming, iterative tasks of ML model development.
///////////2.aml
The best algorithm found is VotingEnsemble with an accuracy of 92.018%. 

### Deploy the best model:
This means shipping the trained model into production, so that it can be consumed by other users as well. Configuring deplowment settings means making choices on cluster settings like memory, cpu/gpu, and other type of interactions like authentication etc.
The best model obtained is then depoyed using Azure Container INstance (ACI) and authentication is enabled.
///////////////////3.deploy-bestmodel
### Enable Logging:
Logging works as a forefront of discovering irregularities in the service. Enabling logging allows a cloud service like Azure about how the deployed service is behaving. We enable application insights in logs.py and then run the script to view the logs generated.
////////////////////////////4.logs
//////////////////////////////////5.app-insights-true
### Swagger Documentation
Swagger is a tool that eases the documentation efforts of HTTP APIs. It makes it easier to explain what type of GET and POST requests are accepted, an example of type of input it accepts, etc. We run the swagger.sh script to run the docker instance for swagger and set a local server using the serve.py script.
/////////////////////////////////////6.swagger-post
### Consume model endpoint
Once a model has been deployed, an endpoint will be available which allows user to send inputs to the trained model and get a response back. This is called as consuming deployed service.HTTP POST is a request method that is used to submit data and HTTP GET is used to retrieve information from a URL. endpoint.py script is used for the same.
////////////////////////////7.endpoint-py
### Benchmark the endpoints
Benchmarking means setting a baseline as an acceptable performance measure. Here we use apache benchmark to see the model performance against our HTTP requests.
////////////////////8.benchmark
### Create and Publish a pipeline
Pipelines are a great way to automate workflows. Publishing a pipeline is the process of making a pipeline publicly available. We use the code in the Jupyter Notebook to create our pipeline.
/////////////////////////////////////////////////9.create-pipeline
We can also view the graph of pipeline endpoint. We can see that it has active status:
///////////////////////////////////10.pipeline graph
Bank marketing model summary in graph, the status for experiment is 'completed'.
/////////////////////////////////11.endpoint-completed
Status of Run Widget, after publishing the pipeline
////////////////////////////////////////////////////////12.run-details


## Screen Recording
Here's a demo of endpoint and pipeline created in this project- //////////////////LINK
