# minikube
Installation Script for microk8s


In short, microk8s is designed to be a fast and lightweight upstream Kubernetes 
install isolated from your host but not via a virtual machine. This isolation is
achieved by packaging all the upstream binaries for Kubernetes, Docker.io, 
iptables, and CNI in a single snap package. The snap package is an application 
container?—?you can imagine this as a lighter weight version of a Docker 
container. It uses a lot of the same underlying technologies for isolation just 
without all the overhead of network isolation.

Installing SNAP on Centos
   https://computingforgeeks.com/install-snapd-snap-applications-centos-7/

Installing Kubernetes (microk8s)
   https://microk8s.io/

Path to microk8s.* Binaries
    /var/lib/snapd/snap/bin/

Start nginx Containers
    microk8s.kubectl run nginx --image nginx --replicas 3
    microk8s.kubectl expose deployment nginx --port 80 --target-port 80 --type ClusterIP --selector=run=nginx --name nginx
    microk8s.kubectl get all
    curl http://localhost

Remove nginx 
    microk8s.kubectl delete deployment/nginx
    microk8s.kubectl get all
    microk8s.kubectl delete svc/nginx

Remove microk8s
    microk8s.disable dashboard dns
    sudo snap remove microk8s

