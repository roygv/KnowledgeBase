# Install
```
curl -s https://raw.githubusercontent.com/k3d-io/k3d/main/install.sh | bash
k3d cluster create mycluster
kubectl create namespace <namespace>
```
# Cheatsheet
```
kubectl cluster-info
kubectl config view  # Cluster configuration
kubectl get namespaces
kubectl config set-context –current –namespace=<name>  # set default namespace
```
