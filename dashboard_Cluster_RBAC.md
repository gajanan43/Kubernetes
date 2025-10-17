# Dashboard of K8S:

## 🧭 **1. Start Minikube**

```bash
minikube start
```

---

## 🧩 **2. Enable the Dashboard Add-on**

Minikube comes with a built-in dashboard add-on. You can enable it with:

```bash
minikube addons enable dashboard
```

You can verify it’s enabled using:

```bash
minikube addons list
```

You should see:

```
| dashboard               | enabled ✅  |
```

---

## 🖥️ **3. Launch the Dashboard**

To start and access the dashboard:

```bash
minikube dashboard
```

This command will:

* Deploy the Kubernetes Dashboard UI.
* Automatically open it in your **default web browser**.

If it doesn’t open automatically, Minikube will show a URL — you can open that manually.

---

## 🧑‍💻 **4. (Optional) Access Dashboard via Token**

Sometimes the dashboard requires a login token for security.
You can get the token using:

```bash
kubectl -n kubernetes-dashboard create token admin-user
```

If that doesn’t work, you can create a **ServiceAccount** and **ClusterRoleBinding** manually (next section).

---

## 🧾 **5. (Optional) Create Admin Access Manually**

If you can’t log in or need admin privileges:

Create a YAML file named `dashboard-adminuser.yaml`:

```yaml
apiVersion: v1
kind: ServiceAccount
metadata:
  name: admin-user
  namespace: kubernetes-dashboard
---
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRoleBinding
metadata:
  name: admin-user
roleRef:
  apiGroup: rbac.authorization.k8s.io
  kind: ClusterRole
  name: cluster-admin
subjects:
- kind: ServiceAccount
  name: admin-user
  namespace: kubernetes-dashboard
```

Apply it:

```bash
kubectl apply -f dashboard-adminuser.yaml
```

Then, get the token:

```bash
kubectl -n kubernetes-dashboard create token admin-user
```

Use this token to log in to the dashboard.

---

## 🛰️ **6. Access the Dashboard Again (Manually)**

If the dashboard stops or you want to reconnect:

```bash
kubectl proxy
```

Then open in browser:

```
http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/http:kubernetes-dashboard:/proxy/
```

---

## ✅ **You Now Have a Running Dashboard**

You can:

* View all resources (Pods, Deployments, ReplicaSets, etc.)
* Create/delete resources
* Monitor cluster health
* Debug workloads visually

---

Would you like me to show **how to deploy your own app (e.g., Apache, React app, or your IoT system)** and **visualize it inside this dashboard**? I can walk you through that next.
