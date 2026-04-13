
# 💻 Compute Services in Microsoft Azure

## App Services, Containers (ACI + AKS), Serverless (Functions)

---

# 🌐 Azure App Services (Web Apps, APIs)

---

## 🗣️ What is Azure App Service?

“Azure App Service is a **fully managed platform (PaaS)** to build and host web apps and APIs.”

👉 You don’t manage:

* OS
* Servers
* Patching

👉 You only focus on:

* Code

---

## 🧠 Analogy

VM = You cook everything 🍳
App Service = Restaurant serves you food 🍽️

---

## 📦 Architecture Diagram

<img width="156" height="142" alt="image" src="https://github.com/user-attachments/assets/39236bb4-f5ac-43dd-89e9-b7fed60cfd79" />

---

## 🧠 Real-Life Use Cases

* Hosting websites
* REST APIs
* Backend services

---

## 🎯 Key Features

* Auto-scaling
* Built-in load balancing
* Deployment from GitHub
* SSL support

---

## 🛠️ Hands-On: Create a Web App

---

### 👉 Step 1:

Go to Azure Portal → Search **App Services** → Click **Create**

---

### 👉 Step 2: Basics

* Resource Group → `Demo-RG`
* Name → `demo-webapp-123` (must be unique)
* Runtime → Node.js / .NET / Python
* Region → Central India

---

### 👉 Step 3: App Service Plan

* Create new plan
* Pricing → Free Tier (F1)

---

### 👉 Step 4: Review + Create

Click **Create**

---

## 🧪 Test Your App

👉 After deployment:

* Open URL → `https://demo-webapp-123.azurewebsites.net`

---

## 🎯 Bonus (Deployment)

* Connect GitHub repo
* Auto-deploy on push

---

## ⚖️ App Service vs VM

| Feature     | VM     | App Service |
| ----------- | ------ | ----------- |
| OS control  | Full   | None        |
| Maintenance | Manual | Managed     |
| Deployment  | Manual | Easy        |

---

# 📦 4. Containers

---

## 🗣️ What is a Container?

“A container packages:

* Code
* Dependencies
* Runtime

👉 So it runs **anywhere consistently**”

---

## 🧠 Analogy

Container = Packed lunch box 🍱
Runs same everywhere

---

---

# 🚀 4A. Azure Container Instances (ACI)

---

## 🗣️ What is ACI?

“ACI lets you run containers **without managing servers or orchestration**.”

👉 Simple, fast, lightweight

---

## 📦 Diagram

<img width="203" height="150" alt="image" src="https://github.com/user-attachments/assets/7abbe238-6faf-486e-a0ec-d1ace981d1aa" />

---

## 🧠 Use Cases

* Short-lived jobs
* Testing containers
* Background tasks

---

## 🛠️ Hands-On: Run a Container in ACI

---

### 👉 Step 1:

Search → **Container Instances** → Create

---

### 👉 Step 2:

* Resource Group → `Demo-RG`
* Name → `demo-container`
* Image → `nginx`

---

### 👉 Step 3:

* DNS Name → `demoaci123`

---

### 👉 Step 4:

Click **Create**

---

## 🧪 Test

👉 Open:
`http://demoaci123.<region>.azurecontainer.io`

---

---

# ☸️ 4B. Azure Kubernetes Service (AKS)

---

## 🗣️ What is AKS?

“AKS is a **managed Kubernetes service** to run containerized applications at scale.”

---

## 🧠 Analogy

ACI = Single food stall 🍜
AKS = Full food delivery system 🍔🚚

---

## 📦 Diagram

<img width="272" height="152" alt="image" src="https://github.com/user-attachments/assets/a7a19f48-0b78-4981-9af3-f270cfb60d8a" />

---

## 🧠 Real-Life Use Cases

* Microservices architecture
* Large-scale applications
* DevOps pipelines

---

## 🎯 Key Features

* Auto-scaling
* Self-healing
* Load balancing
* Rolling updates

---

## 🛠️ Hands-On: Create AKS Cluster (Basic)

---

### 👉 Step 1:

Search → **Kubernetes Services** → Create

---

### 👉 Step 2:

* Resource Group → `Demo-RG`
* Cluster Name → `demo-aks`
* Node Count → 1

---

### 👉 Step 3:

* Node Size → B2s

---

### 👉 Step 4:

Click **Create**

---

## 🧪 Deploy Sample App (Basic Idea)

After creation:

* Use Azure CLI:

```bash
kubectl create deployment nginx --image=nginx
kubectl expose deployment nginx --type=LoadBalancer --port=80
```

---

## ⚖️ ACI vs AKS

| Feature    | ACI        | AKS           |
| ---------- | ---------- | ------------- |
| Complexity | Simple     | Complex       |
| Scaling    | Limited    | Advanced      |
| Use Case   | Small jobs | Large systems |

---

# ⚡ 5. Azure Functions (Serverless)

---

## 🗣️ What is Azure Functions?

“Azure Functions is a **serverless compute service** where you run code without managing servers.”

---

## 🧠 Analogy

VM = Own a car 🚗
App Service = Taxi 🚕
Functions = Uber per ride 🚖

---

## 📦 Diagram

<img width="188" height="150" alt="image" src="https://github.com/user-attachments/assets/7ce8bc77-210a-4b62-8548-59113fd397c3" />

---

## 🧠 Real-Life Use Cases

* API backend
* File processing
* Event-driven automation
* Scheduled jobs

---

## 🎯 Key Features

* Pay per execution
* Auto-scale instantly
* Event-driven

---

## 🛠️ Hands-On: Create Azure Function

---

### 👉 Step 1:

Search → **Function App** → Create

---

### 👉 Step 2:

* Resource Group → `Demo-RG`
* Name → `demo-func-123`
* Runtime → Python / Node

---

### 👉 Step 3:

* Hosting → Consumption plan

---

### 👉 Step 4:

Click **Create**

---

## 🧪 Create Function

1. Go to Function App
2. Click **+ Create Function**
3. Choose:

   * HTTP Trigger

---

## 🧪 Test

👉 Open URL → triggers function

---

# 🧠 Final Comparison (Very Important)

---

| Service     | Type       | Use Case         |
| ----------- | ---------- | ---------------- |
| VM          | IaaS       | Full control     |
| VMSS        | IaaS       | Scalable VMs     |
| App Service | PaaS       | Web apps         |
| ACI         | Containers | Simple container |
| AKS         | Containers | Large systems    |
| Functions   | Serverless | Event-driven     |

---

# 🎯 Real-World Architecture Example

---

“Modern web app setup”

* Frontend → App Service
* Backend → AKS
* Background jobs → Functions
* Quick tasks → ACI

---

# 📝 MCQs

---

**1. Which service is fully managed (PaaS)?**
A. VM
B. App Service
C. AKS
D. VNet

✅ Answer: B

---

**2. Which is serverless?**
A. VM
B. AKS
C. Functions
D. VNet

✅ Answer: C

---

**3. ACI is best for:**
A. Large systems
B. Small container jobs
C. Networking
D. Storage

✅ Answer: B

---

**4. AKS is used for:**
A. Simple apps
B. Databases
C. Container orchestration
D. DNS

✅ Answer: C

---
