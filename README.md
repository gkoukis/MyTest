# EdgeNet demo | CODECO project
This is an EdgeNet demo for the 6 months of the CODECO project

We will deploy two example services to test some basic functionalities of EdgeNet such as the Selective Deployment

## Instructions to run experiments on EdgeNet
Detailed instructions to run experiments on EdgeNet can be found in [EdgeNet-Testbed site](https://www.edge-net.org/pages/running-experiments.html) and the respected [Github](https://github.com/EdgeNet-project/edgenet)

### Prerequisites
To run the following examples you will need:
1. [``kubectl``](https://kubernetes.io/docs/reference/kubectl/overview/), the [Kubernetes](https://kubernetes.io/) command-line interface.

- [Install kubectl on Linux](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux)
- [Install kubectl on macOS](https://kubernetes.io/docs/tasks/tools/install-kubectl-macos)
- [Install kubectl on Windows](https://kubernetes.io/docs/tasks/tools/install-kubectl-windows)
1. a namespace in which you have access such as *<-n mynamespace>* when registered in EdgeNet
1. a configuration file such as *<mycfg.cfg>* downloaded after registered in EdgeNet (this file needs to be replaced every few days to access EdgeNet)
1. the .yaml files


## Deployed services & description
The yaml files:
> *cdnserviceexample.yaml*

The *cdnserviceexample* describes a simple cdn service - a multimedia app - in which EdgeNet picks up some nodes from specific geographic locations as we defined with a selector in the .yaml file to run our service. We can connect to these pods through the CL.

> *ping-me-example.yaml*

In the *ping-me-example* EdgeNet picks up some nodes from specific geographic locations as we defined with a selector in the .yaml file which ping a server or ip address. We can observe the log output of the pods pinging a server or ip address and the delay. If we have access to the server or ip address we can also observe through traffic control (e.g. tcpdump) the received pings from all over the globe. This example highlights the possible use of EdgeNet as a benchmarking tool for the CODECO usecases i.e. setting up clients (around the globe) to test the provided services.


## General
> Get a list of the contributed EdgeNet nodes
~~~~
kubectl get nodes -o wide --kubeconfig <mycfg.cfg> -n <mynamespace>
~~~~
> Get a detailed description of a contributed EdgeNet node
~~~~
kubectl describe <node_name> --kubeconfig <mycfg.cfg> -n <mynamespace>
~~~~

## Deployment & Check
+ First .yaml
> Deploy the cdnserviceexample service
~~~~
kubectl apply -f cdnserviceexample.yaml --kubeconfig <mycfg.cfg> -n <mynamespace>
~~~~
A Selective Deployment datastructure is created which let us deploy our service based on the selector we defined in the .yaml file
> Check the Selective Deployment, Deployments, Services, Pods
~~~~
kubectl get sd --kubeconfig <mycfg.cfg> -n <mynamespace>
~~~~
~~~~
kubectl get deployments --kubeconfig <mycfg.cfg> -n <mynamespace>
~~~~
~~~~
kubectl get services --kubeconfig <mycfg.cfg> -n <mynamespace>
~~~~
~~~~
kubectl get pods --kubeconfig <mycfg.cfg> -n <mynamespace>
~~~~

> Connect to a pod running our service with CL
~~~~
kubectl exec -it <cdn-server-podname> bash --kubeconfig <mycfg.cfg> -n <mynamespace>
~~~~
> Connect a local port to a port of a pod
~~~~
kubectl port-forward <cdn-server-podname> 8080:80 --kubeconfig <mycfg.cfg> -n <mynamespace>
~~~~


---
+ Second .yaml
> Deploy the ping-me-example service
~~~~
kubectl apply -f ping-me-example.yaml --kubeconfig <mycfg.cfg> -n <mynamespace>
~~~~
> Get the log output of a pod
~~~~
kubectl logs <ping-source-podname> --kubeconfig <mycfg.cfg> -n <mynamespace>
~~~~
> If server or ip address is accessible, observe the pings from the pods through tcpdump
~~~~
sudo tcpdump -i <eth0> icmp
~~~~

## Delete the services
~~~~
kubectl delete -f cdnserviceexample.yaml --kubeconfig <mycfg.cfg> -n <mynamespace>
~~~~
~~~~
kubectl delete -f ping-me-example.yaml --kubeconfig <mycfg.cfg> -n <mynamespace>
~~~~
