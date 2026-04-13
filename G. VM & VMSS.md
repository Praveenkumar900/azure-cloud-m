* Virtual Machines (VMs)

* VM Scale Sets

---

# 🖥️ 1. Virtual Machines (VMs)

---

## 🗣️ What is a Virtual Machine?

“A Virtual Machine is a **computer running in the cloud**.”

👉 It behaves like a real machine:

* Has CPU, RAM, Disk
* You install OS (Windows/Linux)
* You control everything

---

## 🧠 Real-Life Analogy

“Think of VM as renting a computer in a data center.”

* Your laptop → local machine
* VM → remote machine in Microsoft Azure

---

## 🧱 Key Components of a VM

* OS (Windows/Linux)
* CPU & RAM (size)
* Disk (storage)
* Network (IP inside VNet)

---

## 📦 Architecture Diagram

<img width="199" height="161" alt="image" src="https://github.com/user-attachments/assets/bd877a3b-93f5-4c5c-b012-933d07e8988a" />

---

## 🧠 Use Cases

* Hosting websites
* Running legacy applications
* Testing environments
* Custom software

---

## ⚠️ Responsibility (Important)

VM = IaaS

👉 You manage:

* OS updates
* Security patches
* Software

---

## 🛠️ Hands-On: Create a Virtual Machine

---

### 👉 Step 1: Go to Azure Portal

Search → **Virtual Machines** → Click **Create**

---

### 👉 Step 2: Basics

* Resource Group → `Demo-RG`
* VM Name → `demo-vm`
* Region → `Central India`
* Image → Ubuntu Server
* Size → Standard B1s

---

### 👉 Step 3: Authentication

* Username → azureuser
* Password or SSH key

---

### 👉 Step 4: Networking

* VNet → Select existing
* Public IP → Enabled

---

### 👉 Step 5: Review + Create

Click **Create**

---

## ▶️ After Deployment

* Connect using SSH / RDP
* Install software

---

## 🧠 Mini Task

👉 SSH into VM and install nginx:

```bash
sudo apt update
sudo apt install nginx -y
```

👉 Open browser → Public IP → see webpage

---

# ⚖️ When to Use VMs?

Use VMs when:

* You need full control
* You install custom software
* Legacy apps

---

# 📈 2. Virtual Machine Scale Sets (VMSS)

---

## 🗣️ What is VM Scale Set?

“VM Scale Set lets you **automatically create and manage multiple VMs**.”

👉 Instead of 1 VM → many identical VMs

---

## 🧠 Problem It Solves

“If 1 VM gets too much traffic → it crashes”

👉 Solution:

* Add more VMs automatically

---

## 📦 Diagram

```id="vmss1"
User Traffic
     ↓
Load Balancer
     ↓
VM Scale Set
 ├── VM1
 ├── VM2
 ├── VM3
```

---

## 🧠 Real-Life Example

E-commerce sale:

* Normal → 2 VMs
* Sale → auto-scale to 10 VMs

---

## 🎯 Features

* Auto scaling
* High availability
* Load balancing

---

## ⚙️ Scaling Types

### 🔹 Manual Scaling

You set number of VMs

### 🔹 Auto Scaling

Based on:

* CPU usage
* Memory
* Traffic

---

## 🛠️ Hands-On: Create VM Scale Set

---

### 👉 Step 1

Search → **Virtual Machine Scale Sets** → Create

---

### 👉 Step 2: Basics

* Resource Group → `Demo-RG`
* Name → `demo-vmss`
* Image → Ubuntu
* Size → B1s

---

### 👉 Step 3: Instance Count

* Initial instances → 2

---

### 👉 Step 4: Scaling Policy

* Enable auto-scale
* Example rule:

  * CPU > 70% → add 1 VM
  * CPU < 30% → remove VM

---

### 👉 Step 5: Networking

* Attach to VNet
* Load Balancer → Create new

---

### 👉 Step 6: Review + Create

---

## ▶️ After Deployment

* Azure automatically manages VMs
* You don’t log into each individually

---

## 🧠 Mini Task

* Increase traffic (simulate load)
* Watch VM count increase

---

# ⚖️ VM vs VM Scale Set

---

| Feature   | VM         | VM Scale Set      |
| --------- | ---------- | ----------------- |
| Instances | Single     | Multiple          |
| Scaling   | Manual     | Auto              |
| Use Case  | Small apps | High traffic apps |

---

👉 “VM = one machine
👉 VMSS = group of machines with auto scaling”

---

# 📝 MCQs

---

**1. VM is an example of:**
A. SaaS
B. PaaS
C. IaaS
D. Serverless

✅ Answer: C

---

**2. VM Scale Set is used for:**
A. Storage
B. Scaling VMs
C. DNS
D. Security

✅ Answer: B

---

**3. Auto-scaling is based on:**
A. Time only
B. CPU/metrics
C. DNS
D. Storage

✅ Answer: B

---

**4. Which gives more control?**
A. App Service
B. VM
C. Functions
D. AKS

✅ Answer: B

---
