---
title: "Key Concepts from Microsoft Containers OpenHack with Kubernetes and AKS"
excerpt: ""
header:
  image: "/assets/images/Keep-Going.jpg"
  caption: ""
date:   "2020-02-28"
categories: 
- "EVENTS"
tags: 
- "OPENHACK"
- "CONTAINERS"
- "DOCKER"
- "KUBERNETES"
- "AKS"
- "AZURE"
---
Azure consultants are constantly looking to expand our scope of expertise and aligning to this I've recently attended a Microsoft Containers OpenHack in Sydney. This event was a huge success for me. It was a rude introduction to K8s and AKS - but in a good way.

![OpenHackLogo](/assets/images/OpenHackLogo1.png)

> Microsoft OpenHack is a developer-focused engagement where a wide variety of participants (Open) learn through hands-on experimentation (Hack) using challenges based on real-world customer scenarios designed to mimic the developer journey.
OpenHack provides a unique and fun upskilling experience for Microsoft employees, customers and partners. Attendees work together in teams to complete challenges that increase in complexity and are actively engaged, requiring deep collaboration, as they learn together. Source: Microsoft

## Retrospective - Day1/Day2/Day3
On the first day hackers were split up between the 20 tables in the room. My team had 2 international attendees and 3 locals (myself included). Everyone was joining with varying levels of real experience with Kubernetes/AKS so things were destined to be kept interesting. 

>My Hacker Team
* Chan - Singapore
* Yong - Korea
* Chris - Australia
* Yegor - Australia
* Jesse (me) - Australia

As part of the fun we took on aliases such as `hacker1`, `hacker2`, `hackerX` and during most of the 8 challenges it felt as if we really did hack together a solution just to pass. And by 'hack' I'm referring to the process of:
* Searching through KB articles for code samples or architecture guidance
* Creating new .YAML config files to apply changes to Kubernetes/AKS
* Testing code samples in Kubectl and AzureCLI via VSCode
* Troubleshooting abstract errors and/or connectivity/security issues
* More searching through KB articles
* More testing of code
* Finally getting something to work and meeting the success criteria

> During the event you can expect that things will break and you will fix it, that's part of the fun. There is no clear path forward and the 'unknown' factor is ever present.

Due to limited time of the OpenHack (3 days) the focus was on completing challenges quickly by meeting the success criteria. This often led us to implement any available solution because there wasn't sufficient time to search for, and go through a `best` vs `sub-optimal` decision. 

After configuring the environment our instructor would have us demonstrate that each success criteria was passed For example: <i>Demonstrate that you are prompted on cluster access to authenticate with AAD.</i> There were some tense moments here as we waited for something, anything to break.

![EscapeRoom](/assets/images/the-cipher-room.jpg)

Personally I liked the layout of the event because, similar to an Escape Room, it seemed as if Microsoft had locked you into the room and to get out you needed to build a working Kubernetes environment on Azure. Hack-a-thons where you have limited time and resources to design and present your submission are also a relative example to Microsoft OpenHack.

## Challenges and Key Concepts
During the Containers OpenHack we had 8 challenges to complete. Unfortunately we ran out of time to do them all but it was a great learning experience anyways. I've tried to compress each challenge to a single paragraph below and include links to the key concepts.

### Challenge 1
We used Docker to build, tag, and push images to Azure Container Registry (ACR) based on the application source code. Docker was also used to pull, run, and configure a SQL Server container in Azure.

- https://docs.docker.com/get-started/
- https://docs.docker.com/engine/reference/builder/
- https://docs.docker.com/engine/reference/commandline/cli/
- https://docs.docker.com/network/
- https://docs.microsoft.com/en-us/azure/container-registry/
- https://docs.microsoft.com/en-us/azure/container-registry/container-registry-tutorial-quick-task
- https://docs.microsoft.com/en-us/sql/linux/quickstart-install-connect-docker?view=sql-server-2017&pivots=cs1-bash
- https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-configure-docker?view=sql-server-ver15

### Challenge 2
We created an Azure Kubernetes Service (AKS) cluster and configured environment variables for the app's microservices to connect to eachother, then deployed the app into the AKS cluster.

- https://docs.microsoft.com/en-us/azure/aks/concepts-clusters-workloads
- https://kubernetes.io/docs/concepts/services-networking/connect-applications-service/
- https://kubernetes.io/docs/concepts/services-networking/dns-pod-service/
- https://kubernetes.io/docs/tasks/access-application-cluster/port-forward-access-application-cluster/
- https://kubernetes.io/docs/tasks/access-application-cluster/create-external-load-balancer/
- https://kubernetes.io/docs/reference/kubectl/overview/
- https://docs.microsoft.com/en-us/azure/aks/kubernetes-walkthrough
- https://docs.microsoft.com/en-us/cli/azure/aks?view=azure-cli-latest#az-aks-create
- https://docs.microsoft.com/en-gb/azure/aks/cluster-container-registry-integration

### Challenge 3
We configured a dedicated VNET/Subnet for the AKS cluster and setup Azure Container Networking Interface (CNI). We also setup AAD integration for cluster authentication.

- https://docs.microsoft.com/en-us/azure/aks/concepts-identity
- https://docs.microsoft.com/en-us/azure/aks/azure-ad-integration-cli
- https://docs.microsoft.com/en-us/azure/aks/control-kubeconfig-access
- https://docs.microsoft.com/en-us/cli/azure/ad?view=azure-cli-latest
- https://docs.microsoft.com/en-us/azure/aks/configure-azure-cni

### Challenge 4
We configured Kubernetes namespaces and RBAC bindings to assign access to different teams. We used Key Vault FlexVolume and Azure KeyVault to secure our environment secrets. We also created Kubernetes Ingress Controllers for inbound Layer 7 traffic forwarding to our services.

- https://github.com/Azure/kubernetes-keyvault-flexvol
- https://docs.microsoft.com/en-us/azure/aks/concepts-network#ingress-controllers
- https://docs.microsoft.com/en-us/azure/aks/ingress-basic
- https://docs.microsoft.com/en-us/azure/aks/operator-best-practices-cluster-security
- https://docs.microsoft.com/en-us/azure/aks/concepts-identity#role-based-access-controls-rbac
- https://docs.microsoft.com/en-us/azure/aks/azure-ad-rbac

### Challenge 5
We setup monitoring, logging, and alerts for the AKS cluster and implemented resource limits on a newly deployed application which was resource-hungry.

- https://docs.microsoft.com/en-us/azure/architecture/microservices/logging-monitoring
- https://docs.microsoft.com/en-us/azure/azure-monitor/insights/container-insights-overview
- https://docs.microsoft.com/en-us/azure/azure-monitor/insights/container-insights-agent-config
- https://docs.microsoft.com/en-us/azure/azure-monitor/insights/container-insights-log-search#search-logs-to-analyze-data
- https://docs.microsoft.com/en-us/azure/kusto/
- https://docs.microsoft.com/en-us/azure/azure-monitor/insights/container-insights-alerts
- https://prometheus.io/docs/introduction/overview/
- https://github.com/helm/charts/tree/master/stable/nginx-ingress#prometheus-metrics
- https://prometheus.io/docs/instrumenting/exporters/
- https://prometheus.io/docs/prometheus/latest/querying/examples/#using-functions-operators-etc
- https://prometheus.io/docs/visualization/grafana/

### Challenge 6
We looked into enhancing cluster security by applying restrictions to traffic and app access. Ultimately the team decided not to pursue this challenge due to time constraints.

- https://kubernetes.io/docs/reference/access-authn-authz/service-accounts-admin/
- https://docs.microsoft.com/en-us/azure/aks/use-pod-security-policies
- https://docs.microsoft.com/en-us/azure/aks/use-network-policies
- https://docs.microsoft.com/en-us/azure/aks/api-server-authorized-ip-ranges
- https://docs.microsoft.com/en-us/azure/aks/limit-egress-traffic
- https://docs.microsoft.com/en-us/azure/sql-database/sql-database-vnet-service-endpoint-rule-overview
- https://docs.microsoft.com/en-us/cli/azure/network/vnet/subnet?view=azure-cli-latest#az-network-vnet-subnet-update
- https://docs.microsoft.com/en-us/cli/azure/sql/server/firewall-rule?view=azure-cli-latest

### Challenge 7
We deployed an AKS Windows cluster and Windows Nodepools. We also configured Taints on the Nodepools and Tolerations on Pods to allow deployment of Linux and Windows containers to the same AKS cluster.

- https://kubernetes.io/docs/setup/production-environment/windows/intro-windows-in-kubernetes/
- https://docs.microsoft.com/en-us/azure/aks/use-multiple-node-pools
- https://docs.microsoft.com/en-us/azure/aks/windows-container-cli
- https://docs.microsoft.com/en-us/virtualization/windowscontainers/about/

### Challenge 8
We looked into deploying a service mesh into the AKS cluster using either Linkerd or Istio. The service mesh would have provided capabilities like traffic management and resiliency to our workloads and decoupled these capabilities from the application layer to the infrastructure layer. Ultimately we ran out of time here and were not able to get it working.

- https://docs.microsoft.com/en-us/azure/aks/servicemesh-about
- https://linkerd.io/2/getting-started/
- https://docs.microsoft.com/en-us/azure/aks/servicemesh-linkerd-about
- https://docs.microsoft.com/en-us/azure/aks/servicemesh-linkerd-install?pivots=client-operating-system-linux
- https://istio.io/docs/concepts/what-is-istio/
- https://docs.microsoft.com/en-us/azure/aks/servicemesh-istio-about
- https://docs.microsoft.com/en-us/azure/aks/servicemesh-istio-install?pivots=client-operating-system-linux

## Closing Remarks

![ChallengeComplete](/assets/images/OpenHackContainersChallenge.png)

My first Microsoft OpenHack was a great experience, I went in with low expectations and came away with more hands-on experience with Kubernetes and AKS than I would've hoped to achieve in 3 days.

Check out if there's an event coming near you - [https://openhack.microsoft.com/][OpenHack]

Cheers,
Jesse

[OpenHack]:https://openhack.microsoft.com/