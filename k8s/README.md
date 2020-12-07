# Installing the FIWARE Marketplace on Kubernetes with Helm

The following describes how to setup a full instance of the FIWARE Marketplace. This includes the 
Business API Ecosystem itself, as well as the required databases and the IdM (Keyrock).

This repository provides examples of the Helm values files (`values-*.yml`) which show the minimum configuration 
parameters to be set. Adapt these for your setup before proceeding with the instructions.

The helm chart with all possible configuration values can be found here:
* [Sources](https://github.com/FIWARE/helm-charts/tree/main/charts/business-api-ecosystem)
* [Artifact HUB](https://artifacthub.io/packages/helm/fiware/business-api-ecosystem)



## Preparation

Prepare Helm repositories
```shell
helm repo add t3n https://storage.googleapis.com/t3n-helm-charts
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo add fiware https://fiware.github.io/helm-charts/
helm repo update
```

Create a namespace for the Marketplace instance.
```shell
# Namespace for Marketplace
export MPNS="marketplace"
kubectl create ns $MPNS
```

In the following we assume that you have control of the domain `domain.org`. Furthermore we assume 
that the externally available components will be accessible on the following subdomains:
* Keyrock IdM: https://keyrock.domain.org
* Marketplace UI (Logic Proxy): https://marketplace.domain.org



## Databases

Install the required databases MongoDB and MySQL. 
```shell
# Deploy MySQL:
helm install -f ./values-mysql.yml --namespace $MPNS mp-mysql t3n/mysql

# Deploy MongoDB
helm install -f ./values-mongodb.yml --namespace $MPNS mp-mongodb bitnami/mongodb
```



## IDM

Install the Keyrock IdM. Make sure to setup an Ingress or OpenShift route in the values file for external 
access of the UI (e.g. https://keyrock.domain.org).
```shell
# Deploy Keyrock
helm install -f ./values-keyrock.yml --namespace $MPNS mp-keyrock fiware/keyrock
```

In a browser open the Keyrock UI (e.g. https://keyrock.domain.org) and login with the admin credentials.

Create an application for the FIWARE Marketplace
* Set the URL of the Marketplace UI (e.g. https://marketplace.domain.org)
* Set the Callback URL for the OAuth2 Authorization Code flow (e.g. https://marketplace.domain.org/auth/fiware/callback)
* Enable the 'Authorization Code' and 'Refresh Token' grant types

On the next screen, create the following roles:
* admin
* seller
* customer
* orgAdmin

After finishing the creation of the application, note down the shown OAuth2 ClientID and ClientSecret.



## Business API Ecosystem (FIWARE Marketplace)

Finally install the Business API Ecosystem. Make sure to setup an Ingress or OpenShift route in the values file for external 
access of the Marketplace UI (e.g. https://marketplace.domain.org). Furthermore adapt the configuration options for 
the setup databases and Keyrock instance.
```shell
# Deploy BAE FIWARE Helm Chart
helm install -f ./values-marketplace.yml --namespace $MPNS mp fiware/business-api-ecosystem
```

The deployment of all components will take some time. When the logic proxy component has been deployed and the running state, 
you can access the marketplace UI via the browser (e.g. http://marketplace.domain.org).

Before logging in, you might need to setup some users within Keyrock and assign corresponding roles (e.g. customer or seller).

