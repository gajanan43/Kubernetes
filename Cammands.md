1) minikube start → Creates/starts your cluster.
2) minikube stop → Pauses your cluster (resources freed, but data saved).
3) minikube delete → Destroys your cluster completely.
4) Kubectl get nodes → Show all the working or existing nodes in cluster
5) kubectl config get-contexts → See all available contexts (kind, minikube)
6) kubectl config use-context <context-name> → Switch to another cluster
7) kubectl get namespace(ns) → Show all the namespaces in the cluster
8) kubectl create ns <namespace-name> → Create a namespace in the cluster
9) kubectl delete ns <namespace-name> → Delete a existing namespace in the cluster
10) kubectl get pods → Show all pods in the namespace
11) kubectl run nginx --image=nginx → Pod was create in the default namespace
12) kubectl run nginx --image=nginx -n nginx → nginx Pod was create in the nginx namespace
13) kubectl get pods -n <namespace-name> → Show all pods in the specific namespace
14) kubectl delete pod <pod-name> → Delete the pod
15) 





