---
layout: post
title: Kubernetes deployment of Graylog - Structure and Key Concepts
description: A follow up post, this will let you know Graylog essential details required to run in Kubernetes. Lets Start !
date: 2017-8-05
categories:
  - internship
  - kubernetes
  - graylog
comments: true
---

This post is follow up from the deployment of Graylog in Docker.
My internship was a success, as I was finally able to deploy the Graylog service in GCE as well as AWS using Kubernetes.

I am not going to discuss in this post the vary details of the configuration files, but the structure that I used, and the key concepts that might help one progress quickly over the problems that I faced.

## STRUCTURE

For setting up the Graylog service, one needs to deploy ElasticSearch, Mongo DB, and Graylog. I created 3 services, so that they can be scaled independently. The services composed of stateful sets that used Persistent disks in their pods. Each of the services were connected using the enviromental variables that one need to declare and assign in the configuration. This sounds simple, but something like Graylog which doesnt have a proper documentation in Kubernetes, takes a lot of struggle for API Connections.

## KEY CONCEPTS USED

Connecting the rest apis and managing the workign of pods was difficult. One must know that they should use stateful sets and derefernce pods based on their IPs that they are assigned as they are  stateful. This IP points to the pod and is used in the enviroment variables.

Graylog requires mongo db replica set in action. But what did I create ? It was a stateful set! Then ? We must provide proper commnands in the mongo db, so that the stateful set is identified and implemented as a replica set. This can be found on googling.

The next important thing is scaling and resource management. One must take care of the percent of resources that are being used in the nodes and restrict them accordingly to avoid node failures. 

The graylog service wont work if you dont allow firewall rules (in GCE) to let access the service from your ip address. This is something of a basic info, but a important one. 

