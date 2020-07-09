# Getting Started with Prometheus - scottyfullstack.com

Folder Structure of our Project  

.  
├── configs  
│   ├── alertmanager.yml  
│   ├── prometheus.yml  
│   └── rules.yml  
├── deployment.yml  
├── permissions  
│   └── permissions.yml  
└── README.md  

## Hello App with Exporter  
This app can be found in the docker repository sparlor/scottyfullstack:hello  

## ./configs/*
This folder containes our config yamls for alertmanager and prometheus (rules + prom conf).  
We create these as configmaps for our kube cluster so that we don't have to rebuild a custom prometheus image every time we need to make a configuration change.  

## ./permissions/permissions.yml
This folder contains three files in one: ClusterRole, Service Account, and ClusterRoleBinding for rbac.  
This is so that Prometheus can access the metrics of our hello.py app.  

## ./deployment.yml
This is the deployment yaml for Prometheus. This includes a container for both Prometheus and Alertmanager, as well as Volume definitions tied to our configs mentioned above.  