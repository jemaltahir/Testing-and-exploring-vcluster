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

### Codes used for demo
```
# Requirements

kubectl version
helm version
vcluster --version

# Check k8s cluster
kubectl config view
minikube status 
minikube start --driver=kvm2 --kubernetes-version v1.22.2


kubectl create namespace ns1

vcluster create vcl1 -n ns1

kubectl config view
kubectl config get-contexts       # display list of contexts
kubectl config current-context    # display the current-context
kubectl config use-context minikube # to change context 

kubectl get pods -n ns1 
kubectl get statefulset -n ns1
vcluster connect -n ns1 vcl1 -- bash # or portforwarding 
kubectl get deployments.apps -n ns1 
kubectl get pods -n ns1 
kubectl config use-context vcluster_vcl1_ns1_minikube 
kubectl get namespaces 
kubectl get pods -n testns 
kubectl get svc -n testns 
kubectl get all -n testns 
kubectl scale deployment --replicas=3
kubectl scale deployment --replicas=3 -n testns 
kubectl get deployments.apps -n testns 
kubectl scale deployment nginx-deployment --replicas=3 -n testns 
kubectl get deployments.apps -n testns 
kubectl get pods  -n testns 
kubectl config use-context minikube 
kubectl get pods -A
kubectl get deployments.apps 
kubectl get pods -A

# Cleaning up
miniku delete
rm -rf ~/.minikube/
rm -rf ~/.kube/
rm -rf /tmp/3* 
rm -rf /tmp/minikube*
ls /tmp/
```
