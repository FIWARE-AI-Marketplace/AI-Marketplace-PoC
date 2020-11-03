====================
Proof of concept
====================

.. note::
   This document needs content


Introduction to the PoC

* General description of the proof of concept
* Showcase for the activation and usage of an AI service offered via the marketplace
* Brief introduction of the 3 parties involved: marketplace, AI service and consumer



-----------------
Use cases
-----------------

Information about the covered use case

* Description of the covered use cases and the single steps involved.
* Story 1: Consumer activates AI service via marketplace, AI service is already available with a pre-trained model, marketplace notifies AI service about prediction endpoint, subscription to context broker about prediction results, consumer sends updates on current animal state, consumer gets prediction results
* Story 2 (optional): Provider and Consumer process for a data service
* Description should be provided for the 3 different views of involved parties: marketplace, AI service and consumer.




-------------------
Technical Overview
-------------------

Overview of the technical infrastructure splitted into 3 environments: Marketplace environment, AI/ML service run environment, Consumer application environment

* Description and diagrams of the architecture
* AI service: Spark cluster (+ data storage), cosmos connector, PEP
* Marketplace: Standard FIWARE marketplace (business API eco system), API security (keyrock + umbrella service), provisioning of activated AI service
* Consumer: Dashboard application for viewing prediction results, Context Broker for subscribing to prediction results, PEP


* (Optional) Add details when providing a data service




------------------------
AI Service
------------------------

Description and details about the AI Service

* Description of the example AI service to be offered via the marketplace
* Agrifood AI service to predict growths of a cow by tracking its weight
* Dataset description: we will get real life data from the company Senso Wave, the dataset has the following attributes GPS data, animal weight, temperature..(1 million sample in average). Contact person for data:  Ignacio Gomez Maqueda  imaqueda@sensowave.com 
* Computing resources: Depends on the amount of data and the weight of the AI algorithm used. Contact person from UPM: sonsoles.lopez.pernas@alumnos.upm.es  
* Details about implementation
* Weight of each animal in a farm is measured every day 
* Data describing diet of the animal is also registered
* PEP configuration


