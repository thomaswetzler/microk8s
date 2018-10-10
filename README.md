# minikube
<h1>Installation Script for microk8s</h1>
<P>
In short, microk8s is designed to be a fast and lightweight upstream Kubernetes 
install isolated from your host but not via a virtual machine. This isolation is
achieved by packaging all the upstream binaries for Kubernetes, Docker.io, 
iptables, and CNI in a single snap package. The snap package is an application 
container?—?you can imagine this as a lighter weight version of a Docker 
container. It uses a lot of the same underlying technologies for isolation just 
without all the overhead of network isolation.
<P>
Installing SNAP on Centos<br>
   https://computingforgeeks.com/install-snapd-snap-applications-centos-7/
<P>
Installing Kubernetes (microk8s)<br>
   https://microk8s.io/
<P>
Path to microk8s.* Binaries<br>
    /var/lib/snapd/snap/bin/
<P>
Start nginx Containers<br>
    microk8s.kubectl run nginx --image nginx --replicas 3<br>
    microk8s.kubectl expose deployment nginx --port 80 --target-port 80 --type ClusterIP --selector=run=nginx --name nginx<br>
    microk8s.kubectl get all<br>
    curl http://localhost<br>
<p>
Remove nginx <br>
    microk8s.kubectl delete deployment/nginx<br>
    microk8s.kubectl get all<br>
    microk8s.kubectl delete svc/nginx
<p>
Remove microk8s<br>
    microk8s.disable dashboard dns<br>
    sudo snap remove microk8s<br>
<p>
