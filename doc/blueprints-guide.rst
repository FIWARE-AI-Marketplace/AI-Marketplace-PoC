=====================================
Architecture Blueprints
=====================================

.. note::
   This document needs content


What is it about blueprints, asset types and marketplace plugins?

* Introduction to the concept

Plug&play AI/ML services require standard interfaces for the injection of data and the publication of results, in any of its execution phases; during training and when already trained and therefore giving responses. FIWARE components and APIs like NGSI-LD, standard data models and security standards provide a good basis for such standard interfaces.

Using these components, a collection of AI/ML platform blueprints can be defined which will be compliant with the KI-Marktplatz. AI/ML Service providers will get and have to choose the one they will use for development of plug&play-able AI/ML services and one of the things to declare/specify when publishing a plug&play-able AI/ML services is what concrete AI/ML platform reference architecture they comply with. 


----------------------------
Blueprints
----------------------------

Architecture blueprints in the AI Marketplace (blueprint per asset type)

* Description of "Base Spark on Digital Twins" blueprint, assign PoC architecture components to blueprint
* Description of blueprint for data provider service (basic files)
* Description of blueprint for NGSI-LD data resources (mapping to query on Context Broker)

Examples of blueprints:
-----------------------

“Base Spark on Digital Twins”:
A Spark Cluster with the necessary ML extensions
Exchange of digital twin data via NGSI-LD Context Broker
API Management framework based on Keycloack
Tools for uploading initial data
“Trusted Spark on Digital Twins”:
“Base Spark on Digital Twins” blueprint modules
IDS Connecto

An example of AI/ML platform blue print (let's call it "Basic Spark-based" blueprint) will be one based on the integration of:
* A Spark Cluster with the necessary ML extensions supporting the execution of AI/ML algorithms
* A Context Broker, providing the means for requesting and getting predictions ("tell me what is the time until next breakdown of this machine") as well as injecting right-time data from different sources (e.g., measurements from different sensors connected to the machine, or measurements provided by CMM machines measuring the quality of parts produced by the Milling Machine)
* Tools for uploading big data sets (e.g., for initiating the training)
* A  Security and API Management framework which allows to secure access to, and usage of, the NGSI-LD API that the Context Broker provides by consuming applications
* etc
 
The "Trusted Spark-based" blueprint which may be a blueprint that is based on the integration of:
* A Spark Cluster with the necessary ML extensions supporting the execution of AI/ML algorithms
* A Context Broker, providing the means for requesting and getting predictions ("tell me what is the time until next breakdown of this machine") as well as injecting right-time data from different sources (e.g., measurements from different sensors connected to the machine, or measurements provided by CMM machines measuring the quality of parts produced by the Milling Machine)
* Tools for uploading big data sets (e.g., for initiating the training)
* A  Security and API Management framework which allows to secure access to, and usage of, the NGSI-LD API that the Context Broker provides by consuming applications
* An IDS Connector within which all the previous components will be deployed and which will provided additional access and usage control
* etc 

Recipes (Kubernetes recipes recommended at this point) for provisioning each of the KI-Marktplatz compatible platform reference architectures on whatever premises or existing public clouds should be provided.  Thus, an AI/ML service provider who wishes to develop a service called "X" for Predictive Maintenance of Milling Machines may opt for adhering to the "Basic Spark-based" AI/ML Platform blueprint.  Therefore, using the Kubernetes recipes associated to that blueprint, it would provision the platform on top of which it will run its AI/ML service "X".  





---------------------------
Plugin implementation
---------------------------

Information about the plugins to be implemented for the blueprints




