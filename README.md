# Operationalizing Machine Learning

In this project, we work with the Bank Marketing dataset. The dataset contains information about the marketing campaign of a Portuguese Banking Institute. The classification goal is to predict whether a client will subscribe to a term deposit or not. We use Azure to configure a cloud-based machine learning production model, deploy it, and consume it. Atlast, we will also create, publish, and consume a pipeline.

## Architectural Diagram
![Architecture](https://github.com/himanimadaan/nd00333_AZMLND_C2/blob/master/Screenshots/0.architecture.png)

## Key Steps

Key steps involved in this project are:
### Authentication:
   Using authentication with automation is the best way to go. If authentication is not enabled, human interaction will be required which will interrupt the       continuous flow of operations. Hence Continuous Integration and Delivery system (CI/CD) rely on uninterrupted flows.
   Types of Authentication: 1. Key based   2. Token based   3. Interactive 
### Dataset registeration
Create a new dataset by navigating in datasets section from the left panel of Azure studio. Dataset can be created either by using the web url or by uploading the data from local csv.

![Dataset](https://github.com/himanimadaan/nd00333_AZMLND_C2/blob/master/Screenshots/1.dataset.png)

### AutoML Model:
This feature of Azure allows to build ML models with high scale, efficiency and productivity, all while sustaining model quality. Thus automating the time-consuming, iterative tasks of ML model development.
![AML](https://github.com/himanimadaan/nd00333_AZMLND_C2/blob/master/Screenshots/2.AML.png)
The best algorithm found is VotingEnsemble with an accuracy of 92.018%. 

### Deploy the best model:
This means shipping the trained model into production, so that it can be consumed by other users as well. Configuring deplowment settings means making choices on cluster settings like memory, cpu/gpu, and other type of interactions like authentication etc.
The best model obtained is then depoyed using Azure Container INstance (ACI) and authentication is enabled.
![Deploy best model](https://github.com/himanimadaan/nd00333_AZMLND_C2/blob/master/Screenshots/3.deploy-bestmodel.png)
### Enable Logging:
Logging works as a forefront of discovering irregularities in the service. Enabling logging allows a cloud service like Azure about how the deployed service is behaving. We enable application insights in logs.py and then run the script to view the logs generated.
![Logs](https://github.com/himanimadaan/nd00333_AZMLND_C2/blob/master/Screenshots/4.logs.png)
![App Insights](https://github.com/himanimadaan/nd00333_AZMLND_C2/blob/master/Screenshots/5.app-insights-true.png)
### Swagger Documentation
Swagger is a tool that eases the documentation efforts of HTTP APIs. It makes it easier to explain what type of GET and POST requests are accepted, an example of type of input it accepts, etc. We run the swagger.sh script to run the docker instance for swagger and set a local server using the serve.py script.
![Swagger](https://github.com/himanimadaan/nd00333_AZMLND_C2/blob/master/Screenshots/6.swagger-post.png)
### Consume model endpoint
Once a model has been deployed, an endpoint will be available which allows user to send inputs to the trained model and get a response back. This is called as consuming deployed service.HTTP POST is a request method that is used to submit data and HTTP GET is used to retrieve information from a URL. endpoint.py script is used for the same.
![Endpoint](https://github.com/himanimadaan/nd00333_AZMLND_C2/blob/master/Screenshots/7.endpoint-py.png)
### Benchmark the endpoints
Benchmarking means setting a baseline as an acceptable performance measure. Here we use apache benchmark to see the model performance against our HTTP requests.
![Benchmark](https://github.com/himanimadaan/nd00333_AZMLND_C2/blob/master/Screenshots/8.benchmark.png)
### Create and Publish a pipeline
Pipelines are a great way to automate workflows. Publishing a pipeline is the process of making a pipeline publicly available. We use the code in the Jupyter Notebook to create our pipeline.
![Create pipeline](https://github.com/himanimadaan/nd00333_AZMLND_C2/blob/master/Screenshots/9.create-pipeline.png)
We can also view the graph of pipeline endpoint. We can see that it has active status:
![pipeline-graph](https://github.com/himanimadaan/nd00333_AZMLND_C2/blob/master/Screenshots/10.pipeline-graph.png)
Bank marketing model summary in graph, the status for experiment is 'completed'.
![endpoint-complet-status](https://github.com/himanimadaan/nd00333_AZMLND_C2/blob/master/Screenshots/11endpoint-completed.png)
Status of Run Widget, after publishing the pipeline
![Rundetails](https://github.com/himanimadaan/nd00333_AZMLND_C2/blob/master/Screenshots/12.rundetails.png)


## Screen Recording
Here's a demo of endpoint and pipeline created in this project- https://1drv.ms/u/s!Avt8pJRrCCqEhmQxlwMK7R5rAn66?e=tufbxr
