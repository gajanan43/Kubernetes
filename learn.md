# Kubernetes:

```https://github.com/LondheShubham153/kubestarte``` -> All data about a kubernetes how to install a various cluster, etc.

## For windows:
1. Open **PowerShell** (not cmd) as Administrator.

   * Press **Start**, type **PowerShell**, right-click → **Run as administrator**.
   * The prompt should look like:

     ```
     PS C:\Users\HP>
     ```

2. Run:

   ```powershell
   winget install Kubernetes.minikube
   ```

3. Wait for installation to finish.

   * `winget` will automatically put `minikube.exe` in your PATH.

4. Verify installation:

   ```powershell
   minikube version
   ```

### 🔹 Add path:

1. Close your current PowerShell.
2. Press **Start** → type **PowerShell** → right-click → **Run as Administrator**.

   * The title bar should say:

     ```
     Administrator: Windows PowerShell
     ```
3. Now run the correct command again:

```powershell
setx PATH "$($env:PATH);C:\Program Files\Kubernetes\Minikube" /M
```

4. Close PowerShell, open it again (normal user is fine), and check:

```powershell
minikube version
```

---
---




