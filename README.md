# Build-and-deploy-a-containerized-application-to-AKS
In this project, i will create a containerized application to AKS from scratch

1-	Create a cluster (ensure auto scaling and high availability)
2-	Ensure security: The purpose is to reduce the manipulation of credentials, and also to control who has access to what.
3-	Get the credentials 
4-	Create an azure container registry (here, we will store our images and everything)
5-	Build a container
-	Create an ACR file
This file will:
o	configure the service principal I have created so far for our AKS cluster.
o	Create a trust
This will help in the way that “I can talk to you and you can talk to me”. 
o	help in the role base authentication between azure cluster and azure container registry.
-	Create an image from our registry and using our dockerfile

6-	Create our application
We use:
-	 deployment.yml file. 
Syntax: kubectl apply -f ./deployment.ymal
This later will provide information like – where our ACR is located, how our application is going to start, how much memory and CPU we will be using
-	Loadbalancer.yml file
Syntax: kubectl apply -f ./loadbalancer.ymal
It is used to forward 8080 to 80
Check if the services have been created:
Syntax: kubectl get services
An external IP address will be created. Copy that Ip and paste it in a new browser.

