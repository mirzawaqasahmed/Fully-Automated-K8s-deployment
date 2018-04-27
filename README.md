# Fully-Automated-K8s-deployment

*Learnt a lot on k8s here but this little project is now **OBSOLETE** since kubeadm's people are doing an awesome job and released "**phase**" that gives the chance to customize and set up easily a "best practices" cluster with the networking solution of choice.*

*I'll maybe switch everything to an overly customized kubeadm cluster in the future to learn more about kubeadm and see if an ansible template can help in any way or not.

Edit : Working on it here : https://github.com/jpmondet/kubeadm-deployment-unleashed  

## Introduction

This ansible repository provides a quick way to automatically deploy a Kubernetes Cluster inspired by the "[K8s the hard way](https://github.com/kelseyhightower/kubernetes-the-hard-way)" method.

The resulting cluster is meant to be ready to try different networking solutions (and much more, of course!) without layers of abstraction that prevent to understand exactly what's happening under the hood (such as kubeadm which makes everything very ~~too~~ easy to deploy).

We all know about most of the existing networking plugins (*Flannel, Calico, Kube-router, etc..*) but this is a hugely moving ecosystem and having a "ready-to-bench" cluster looks pretty convenient.

## The network topology

I am going to re-use the network topology deployed with the [Fully-Automated-BGP-fabric](https://github.com/jpmondet/Fully-Automated-BGP-fabric) to focus here on the K8s cluster.

## The resulting cluster

You can customize the **global_vars.yaml** to get the subnets you like for your resulting cluster but the defaults are : 

*Diagram to insert here*

## K8s networking solutions

* Standard Cni type bridge : 

```
git clone https://github.com/jpmondet/FullyAutomatedBGPfabric
cd FullyAutomatedBGPfabric
ansible-playbook deploy_network.yml -e "option=5549"
cd -
git clone https://github.com/jpmondet/Fully-Automated-K8s-deployment
cd Fully-Automated-K8s-deployment
ansible-playbook deploy_k8s.yaml
```

* Standard Cni type Kubenet : 
* Calico :
* Cilium :
* Weave :
[...]
