**Installing Portworx through Anthos Config Management**

[Portworx](https://portworx.com) is a software defined storage overlay that allows you to:

- Run containerized stateful applications that are highly-available (HA) across multiple nodes, cloud instances, regions, data centers or even clouds
- Migrate workflows between multiple clusters running across same or hybrid clouds
- Run hyperconverged workloads where the data resides on the same host as the applications
- Have programmatic control on your storage resources

[Anthos Config Management](https://cloud.google.com/anthos/config-management) (ACM) is a key component of Anthos. With Anthos Config Management, you can create a common configuration across all your infrastructure, including custom policies, and apply it both on-premises and in the cloud. 

![](https://raw.githubusercontent.com/portworx/px-anthos-acm/master/anthos_cm.png?raw=true)

This guide explains how to deploy Portworx in Kubernetes clusters registered with Anthos through ACM.

There are 5 steps involved in deploying Portworx through ACM:
1. Create cluster labels and cluster selectors for each cluster where Portworx will be installed
2. Generate the specification for the target Kubernetes cluster through PX-Central
3. Annotate the specification with the selector associated with the label of the target cluster
4. Split the Stork CRD specification to a separate YAML file
5. Commit all the specifications to ACM repo

![](https://raw.githubusercontent.com/portworx/px-anthos-acm/master/acm_px.png?raw=true)
