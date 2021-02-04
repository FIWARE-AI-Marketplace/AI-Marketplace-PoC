AI-Service with "Trusted Spark-based" scheme
=====================================================

This use case depicts the usage guide for providing an AI-service with the "Trusted Spark-based" scheme.

TODO: Description of use case


Architecture
-----------------

The "Trusted Spark-based" blueprint which may be a blueprint that is based on the integration of:


* A Spark Cluster with the necessary ML extensions supporting the execution of AI/ML algorithms
* A Context Broker, providing the means for requesting and getting predictions ("tell me what is the time until next breakdown of this machine") as well as injecting right-time data from different sources (e.g., measurements from different sensors connected to the machine, or measurements provided by CMM machines measuring the quality of parts produced by the Milling Machine)
* Tools for uploading big data sets (e.g., for initiating the training)
* A  Security and API Management framework which allows to secure access to, and usage of, the NGSI-LD API that the Context Broker provides by consuming applications
* An IDS Connector within which all the previous components will be deployed and which will provided additional access and usage control
* etc 



Seller
-----------------

TODO: Instructions for provider/seller, step-by-step guide



Customer
-----------------

TODO: Instructions for consumer/customer, step-by-step guide

