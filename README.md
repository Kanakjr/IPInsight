# IP Insight - Unsupervised Anomaly Detection for Suspicious IP Addresses

![IPInsight-Logo](images/logo.png)

## Introduction

IP Insights algorithm uses statistical modeling and neural networks to capture associations between online resources (such as account IDs or hostnames) and IPv4 addresses. It learns vector representations for online resources and IP addresses. This essentially means that if the vector representing an IP address and an online resource are close together, then it is likey for that IP address to access that online resource, even if it has never accessed it before.

IP insights ingests historical data as (entity, IPv4 Address) pairs and learns the IP usage patterns of each entity. When queried with an (entity, IPv4 Address) event, IP Insights model returns a score that infers how anomalous the pattern of the event is.

For example, when a user attempts to log in from an IP address, if the IP Insights score is high enough, a web login server might decide to trigger a multi-factor authentication system. In more advanced solutions, you can feed the IP Insights score into another machine learning model. Furthermore, you can combine the IP Insight score with other features to rank the findings of another security system.

## Notebook

In the notebook, we use the Amazon SageMaker to train a model on synthetic data. We then use this model to perform inference on the data and show how to discover anomalies. After running this notebook, you should be able to:

* Obtain, transform, and store data for use in Amazon SageMaker,
* Create an AWS SageMaker training job to produce an IP Insights model,
* Use the model to perform inference with an Amazon SageMaker endpoint.
