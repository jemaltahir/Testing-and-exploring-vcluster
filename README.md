# Testing-and-exploring-vcluster
Testing and exploring kubernetes cluster using vcluster. Theg goal is to explore and test the vcluster by install vcluster CLI, deploy virtual clusters, run a kubernetes deployment, and learn possible use-cases for our need.

## Requirements:

- kubectl client `kubectl version`

- helm v3 client `helm version`

- A working kubernetes cluster which have kube-context with access to a Kubernetes `kubectl get namespaces`

## Setting up a Kubernetes cluster using minikube
To follow along you can have your own local cluster that is provisioned using [minikube](https://minikube.sigs.k8s.io/docs/) or [kind](https://kind.sigs.k8s.io/docs/user/quick-start/) clusters.
For minikube we are usning kvm2 driver: 
```
 minikube status 
 minikube start --driver=kvm2 --kubernetes-version v1.22.2
 minikube status 
```

### Install the vcluster cli 
Follow the geeting started from the vcluster [web page](https://www.vcluster.com/docs/getting-started/setup)

`vcluster --version`
