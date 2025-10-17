# Helm:

## 🧭 **Step-by-Step: Install Helm in Minikube**

### **1️⃣ Start Minikube**

Make sure your Minikube cluster is running:

```bash
minikube start
```

Verify it’s active:

```bash
kubectl get nodes
```

You should see one node in `Ready` state.

---

### **2️⃣ Download and Install Helm**

#### 👉 **On Windows (PowerShell):**

```bash
choco install kubernetes-helm
```

> (Requires [Chocolatey](https://chocolatey.org/install) package manager)

#### 👉 **On macOS (Homebrew):**

```bash
brew install helm
```

#### 👉 **On Linux:**

```bash
curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash
```

Then verify installation:

```bash
helm version
```

Expected output:

```
version.BuildInfo{Version:"v3.x.x", ...}
```

---

### **3️⃣ (Optional) Configure Helm Repo**

Add a default Helm chart repository:

```bash
helm repo add stable https://charts.helm.sh/stable
```

Update repo list:

```bash
helm repo update
```

---

### **4️⃣ Deploy a Test Chart (Example: Nginx)**

Run this command to deploy an example app inside Minikube:

```bash
helm install my-nginx oci://registry-1.docker.io/bitnamicharts/nginx
```

Check status:

```bash
helm list
```

You should see:

```
NAME      NAMESPACE  REVISION  STATUS   CHART
my-nginx  default     1         deployed nginx-x.x.x
```

---

### **5️⃣ Verify Deployment**

```bash
kubectl get pods
kubectl get svc
```

You’ll see a `my-nginx` Pod and Service.

To access it locally:

```bash
minikube service my-nginx
```

---

### **6️⃣ Uninstall Helm Release**

If you want to remove the deployment:

```bash
helm uninstall my-nginx
```

---

### ✅ **You Now Have Helm Installed with Minikube**

You can now:

* Install apps like MySQL, WordPress, Prometheus, etc.
* Manage releases with `helm upgrade` / `helm rollback`.
* Use custom `values.yaml` for configurations.

---

Would you like me to show you **how to deploy your IoT-based healthcare system (or any custom app)** using a Helm chart next? I can create a Helm chart structure and explain how to package and deploy it in Minikube.
