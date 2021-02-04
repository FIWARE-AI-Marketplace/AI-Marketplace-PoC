==================================
User Guides for specific use cases
==================================

Plug&play AI/ML services require standard interfaces for the injection of data and the publication of results, in any of its execution phases; during training and when already trained and therefore giving responses. FIWARE components and APIs like NGSI-LD, standard data models and security standards provide a good basis for such standard interfaces.

Using these components, a collection of AI/ML platform blueprints can be defined which will be compliant with the KI-Marktplatz. AI/ML Service providers will get and have to choose the one they will use for development of plug&play-able AI/ML services and one of the things to declare/specify when publishing a plug&play-able AI/ML services is what concrete AI/ML platform reference architecture they comply with. 

This section provides user guides for specific use cases.

Recipes (Kubernetes recipes recommended at this point) for provisioning each of the KI-Marktplatz compatible platform reference architectures on whatever premises or existing public clouds should be provided.  Thus, an AI/ML service provider who wishes to develop a service called "X" for Predictive Maintenance of Milling Machines may opt for adhering to the "Basic Spark-based" AI/ML Platform blueprint.  Therefore, using the Kubernetes recipes associated to that blueprint, it would provision the platform on top of which it will run its AI/ML service "X".

.. toctree::
    :maxdepth: 2

    basic-file
    file-host-external
    data-ngsild-external
    ai-service-base-spark
    ai-service-trusted-spark

 
