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
15) kubectl create -f namespace.yml → Create a Namespace using YAML file
16) kubectl apply -f namespace.yml → Create a Namespace using YAML file
17) kubectl exec -it nginx-pod -n nginx -- bash → Get an interactive shell inside your pod’s container
18) kubectl delete -f pod.yml → Delete all pods that was created from your pod.yml 
19) kubectl scale deployment/nginx-deployment -n nginx --replicas=2 → Scaled deployment name nginx-deployment in the nginx namespace to 2 replicas (pods)
20) kubectl set image deployment/nginx-deployment -n nginx nginx=nginx:1.26.2 → Updates the container image inside your Deployment(Beause of deployment support a rollout)
21) cp deployment.yml replicasets.yml → Cppy all data inside the deployment.yml file into replicasets.yml file
22) kubectl get replicasets -n nginx → It will list all the ReplicaSets in the nginx namespace
23) kubectl get pods -n nginx -o wide → See a detailed list of pods in the nginx namespace
24) kubectl logs pod/demo-job-56dg7 -n nginx → See the output of this given pod(Job: Hello Dosto!)
25) kubectl describe pod/<pod-name> -n nginx → Detailed information about a specific pod
26) kubectl get pv → Shows all PersistentVolumes in the cluster (no -n needed, since PVs are cluster-scoped)
27) kubectl get pvc -n nginx → Show all the Persistent Volumes Claim in the namespace nginx(namespace-scoped)







