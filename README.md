## AKS with Application Gateway Ingress provisioned with Terraform 

The Azure Application Gateway Ingress Controller (AGIC) allows the use of Application Gatway as the ingress for Azure Kubernetes Service (AKS). This repository contains a Terraform example that provisions AKS and Application Gateway with AGIC configured as a native, first-class, AKS add-on. A sample application, azure-vote, demonstrates its usage. Additional configuration samples may be found at https://azure.github.io/application-gateway-kubernetes-ingress/ .

Using AGIC eliminates the need to have another load balancer in front of the AKS cluster and avoids additional hops before requests reach AKS. Unlike a traditional in-cluster ingress controller AGIC communicates directly with Kubernetes pods. As a result AGIC can achieve a [50% lower network latency](https://azure.microsoft.com/en-ca/blog/application-gateway-ingress-controller-for-azure-kubernetes-service/) vs in-cluster ingress controllers. 

![Traditional in-cluster load balancer vs AGIC](https://azurecomcdn.azureedge.net/mediahandler/acomblog/media/Default/blog/ecb8b526-618f-4ae4-9b8d-990d3803d06b.png)

Levaraging Application Gateway's native L7 load balancer AGIC offers a number of additional features including:

* URL routing
* Cookie-based affinity
* TLS termination
* End-to-end TLS
* Support for public, private, and hybrid web sites
* Integrated with Application Gatways web application firewall (WAF)
* Azure native, Microsoft supported solution

AGIC can be installed as a first-class AKS add-on or through Helm. Deploying AGIC as an AKS add-on is much simpler and provides a fully managed experience with automatic updates. 

For more information see:

- [Application Gateway Ingress Controller for Azure Kubernetes Service](https://azure.microsoft.com/en-ca/blog/application-gateway-ingress-controller-for-azure-kubernetes-service/)
- [What is Application Gateway Ingress Controller?](https://docs.microsoft.com/en-us/azure/application-gateway/ingress-controller-overview)
- [Create an Application Gateway ingress controller in Azure Kubernetes Service](https://docs.microsoft.com/en-us/azure/developer/terraform/create-k8s-cluster-with-aks-applicationgateway-ingress)
- https://github.com/Azure/application-gateway-kubernetes-ingress
- https://azure.github.io/application-gateway-kubernetes-ingress/
