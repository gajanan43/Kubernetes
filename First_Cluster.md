

# First Cluster:

If you already have **Docker Desktop** installed, you can start Minikube with Docker:

```powershell
minikube start --driver=docker
```

---

### ✅ Test Kubernetes

Once Minikube starts, check the cluster:

```
kubectl get nodes
```

You should see a node named `minikube` in `Ready` state.

---

