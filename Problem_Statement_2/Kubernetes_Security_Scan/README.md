
# Problem Statement 2: Kubernetes Security Scan

## 📌 Objective
Install a local Kubernetes cluster using Minikube and scan it for security findings using Kubescape. Export the scan results as a JSON file.

---

## 🧰 Tools Used
- **Minikube** (local Kubernetes cluster)
- **Kubescape** (Kubernetes security scanner)
- **Windows PowerShell**

---

## 🛠️ Setup & Execution

### ✅ Step 1: Start Minikube

```powershell
minikube start --driver=hyperv --hyperv-virtual-switch="Default Switch"
```

> If you're switching from VirtualBox to Hyper-V, delete the existing Minikube cluster:
```powershell
minikube delete
```

---

### ✅ Step 2: Install Kubescape on Windows

Run the following in **PowerShell**:

```powershell
iwr -useb https://raw.githubusercontent.com/kubescape/kubescape/master/install.ps1 | iex
```

Then check the version:

```powershell
kubescape version
```

---

### ✅ Step 3: Scan the Kubernetes Cluster

Run this to scan based on NSA benchmark:

```powershell
kubescape scan framework nsa --exclude-namespaces kube-system
```

---

### ✅ Step 4: Export Findings as JSON

```powershell
kubescape scan framework nsa --format json --output results.json
```

- This creates a `results.json` file in your **current PowerShell directory**.
- Use `Get-Location` to confirm path.
- Use `ii .` to open the folder in File Explorer.

---

## 📄 Deliverable

- `results.json`: The JSON file with Kubernetes security findings from Kubescape.

---
