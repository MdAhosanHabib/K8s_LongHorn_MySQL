# Setting up Longhorn Storage and MySQL in a Kubernetes Cluster
<img width="549" alt="OraToMysql" src="https://github.com/MdAhosanHabib/K8s_LongHorn_MySQL/blob/main/K8sLonghornMysql.jpg">


## Introduction:
In a Kubernetes (K8s) environment, efficient storage management is pivotal for ensuring the reliability and scalability of applications and databases. This document provides an overview of the steps involved in setting up Longhorn storage and deploying a MySQL database in a Kubernetes cluster. By doing so, data persistence, reliability, and scalability are ensured within a K8s environment.

## Prerequisites:
A Kubernetes cluster with at least two worker nodes.

Each worker node must be equipped with an additional 40GB hard disk, which will be utilized for Longhorn storage.

The kubectl and docker utilities should be installed on both the master and worker nodes.

Essential packages such as git, nfs-utils, iscsi-initiator-utils, and wget must be installed on all nodes.

## Setting up Additional Disk on Worker Nodes:
For each worker node, the additional 40GB hard disk should be added and properly formatted. The disk is formatted for storage and subsequently mounted. 
The relevant /etc/fstab entry ensures automatic mounting upon system startup.

## Installing and Setting up Longhorn:
Longhorn is an open-source, cloud-native storage solution for Kubernetes. The Longhorn installation process includes:

Cloning the Longhorn repository and applying a YAML manifest to install Longhorn.

Monitoring the installation process to verify its completion and checking for any errors.

## Configuring Ingress for Longhorn:
An Ingress is set up to allow access to the Longhorn user interface. The Ingress is configured to route traffic to the Longhorn frontend service. 
The user interface can be accessed using the assigned IP and port.

## Setting Up MySQL with Longhorn Storage:
To provide data persistence for MySQL in the Kubernetes cluster, PersistentVolumeClaims (PVCs) and PersistentVolumes (PVs) are defined and created. 
MySQL deployments, services, and pods are configured to use these PVCs. These steps ensure the database data is stored reliably.

## Accessing MySQL:
MySQL is accessible through the LoadBalancer service. Clients can connect to MySQL using tools like the MySQL client from anywhere within the network. Data can be manipulated and databases can be created as required.

## For hands-on implement follow this file
https://github.com/MdAhosanHabib/K8s_LongHorn_MySQL/blob/0a6505bbc7f2c6eb524fc2d6ac72dd5bce983475/longHornMysqlK8s.txt

## Conclusion:
This document outlines the essential steps involved in setting up Longhorn storage and deploying MySQL within a Kubernetes cluster. The setup provides data persistence, reliability, and scalability to applications and databases, thereby ensuring smooth operations and seamless scaling within a Kubernetes environment.
