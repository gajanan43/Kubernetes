
# 🧭 **Helm Setup and Common Commands**

## 🪟 **Installation (on Windows)**

```bash
winget install Helm.Helm
```

---

## ✅ **Verify Installation**

```bash
helm version
```

*Output example:*

```
version.BuildInfo{Version:"v3.19.0", GitCommit:"...", GoVersion:"go1.22.3"}
```

---

## 📁 **View Folder Structure**

```bash
tree
```

Use this to see the chart folder structure (like `apache-helm/`):

```
apache-helm/
├── charts/
├── templates/
│   ├── deployment.yaml
│   ├── service.yaml
│   ├── _helpers.tpl
│   └── NOTES.txt
├── Chart.yaml
└── values.yaml
```

---

# ⚙️ **Helm Basic Commands**

### 1️⃣ **Create a new Helm chart**

```bash
helm create apache-helm
```

---

### 2️⃣ **Install a Helm chart**

```bash
helm install dev-apache apache-helm -n dev-apache --create-namespace
```

> 📌 This installs the chart `apache-helm` into the namespace `dev-apache`.

---

### 3️⃣ **List all Helm releases**

```bash
helm list -A
```

> Shows all releases across all namespaces.

---

### 4️⃣ **Uninstall a Helm release**

```bash
helm uninstall dev-apache -n dev-apache
```

> Deletes all resources associated with that release.

---

### 5️⃣ **Upgrade or Install (if not present)**

```bash
helm upgrade --install dev-apache apache-helm-0.1.0.tgz -n dev-apache
```

> Good for redeploying after making changes.

---

### 6️⃣ **Package your chart (for deployment)**

```bash
helm package apache-helm/
```

*Output:*

```
Successfully packaged chart and saved it to: D:\K8s\helm\apache-helm-0.1.0.tgz
```

---

### 7️⃣ **Add a Helm repository**

```bash
helm repo add stable https://charts.helm.sh/stable
```

---

### 8️⃣ **Update repositories**

```bash
helm repo update
```

> Refreshes the local cache with latest chart info.

---

### 9️⃣ **Install a chart from a repository (e.g., MongoDB)**

```bash
helm install my-release oci://registry-1.docker.io/bitnamicharts/mongodb
```

---

### 🔟 **Show release status**

```bash
helm status dev-apache -n dev-apache
```

> Displays details about deployed resources and chart version.

---

# 🧾 **Template & Dry Run Commands**

### 🧩 **Render Kubernetes YAML (without installing)**

```bash
helm template apache-helm
```

> Useful for seeing the actual manifests Helm will deploy.

---

### 🧪 **Dry Run (simulate installation)**

```bash
helm install dev-apache apache-helm -n dev-apache --dry-run --debug
```

> Helps debug configuration before applying it.

---

# 🧰 **Chart Management**

### 🔍 **Inspect a chart’s information**

```bash
helm show chart apache-helm
```

### 📜 **Inspect values**

```bash
helm show values apache-helm
```

---

# 🧹 **Cleanup**

### Delete namespace and all resources:

```bash
kubectl delete namespace dev-apache
```

---

# 🌐 **Access Application**

After installation, check services and pods:

```bash
kubectl get all -n dev-apache
```

If service type is `ClusterIP`, change it to `NodePort`:

```bash
kubectl edit svc dev-apache-apache-helm -n dev-apache
```

Then access:

```bash
minikube service dev-apache-apache-helm -n dev-apache
```

---

# 🧩 **Advanced Helm Commands (Optional but Useful)**

| Purpose                                 | Command                                                      |
| --------------------------------------- | ------------------------------------------------------------ |
| Rollback to previous release            | `helm rollback dev-apache 1 -n dev-apache`                   |
| Get release history                     | `helm history dev-apache -n dev-apache`                      |
| Lint chart for errors                   | `helm lint apache-helm`                                      |
| Pull a chart locally                    | `helm pull stable/mysql`                                     |
| Delete all Helm releases in a namespace | `helm uninstall $(helm list -q -n dev-apache) -n dev-apache` |

---
---


