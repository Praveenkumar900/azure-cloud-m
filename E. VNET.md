
# 🌐 Virtual Network (VNet) in Microsoft Azure

---

“A **Virtual Network (VNet)** is a **private network in Azure** where your resources can securely communicate.”

👉 It is the **Azure equivalent of your on-premise network**

---

## 🧠 Simple Analogy

* Your home WiFi network = local network
* Azure VNet = your network in the cloud

👉 Devices → Resources (VMs, apps, databases)

---

## 📦 Diagram

<img width="197" height="298" alt="image" src="https://github.com/user-attachments/assets/ee567e40-cc9a-4156-8203-06ee5354ec2d" />

---

## 🧱 Key Components of a VNet

---

### 1. Address Space

👉 This is the **IP range of the VNet**

Example:

* `10.0.0.0/16`

🧠 Meaning:

* Network starts at `10.0.0.0`
* Can have thousands of IPs

---

### 2. Subnets

👉 Subdivisions inside a VNet

Example:

* `10.0.1.0/24` → Web
* `10.0.2.0/24` → App
* `10.0.3.0/24` → DB

---

### 🧠 Why Subnets?

* Organize resources
* Improve security
* Control traffic

---

### 3. Network Security Groups (NSG)

👉 Controls traffic:

* Allow / Deny rules
* Like a firewall

---

### 4. Connectivity

A VNet can connect to:

* Internet
* Other VNets (VNet Peering)
* On-premise network (VPN)

---

## 🧠 Real-Life Example

“You are building an e-commerce app”

👉 VNet design:

* Subnet 1 → Web servers
* Subnet 2 → Backend services
* Subnet 3 → Database

👉 Users access web layer only
👉 Database stays private

---

## 🛠️ Hands-On: Create a VNet (Follow Along)

---

### 👉 Steps in Azure Portal

1. Go to Azure Portal
2. Search → **Virtual Network**
3. Click **+ Create**

---

### Step 1: Basics

* Subscription → Select
* Resource Group → `Demo-RG`
* Name → `Demo-VNet`
* Region → `Central India`

---

### Step 2: IP Addresses

* Address Space → `10.0.0.0/16`
* Subnet:

  * Name → `default`
  * Range → `10.0.0.0/24`

---

### Step 3: Review + Create

* Click **Create**

---

## 🎯 What Just Happened?

You created:

* A private network
* With its own IP range
* Ready to host resources

---

## 🧠 Important Points

* VNet is **isolated by default**
* Resources inside VNet can communicate internally
* Internet access must be configured
* Subnet design is very important

---

## ⚠️ Common Beginner Mistakes

* Using overlapping IP ranges
* Not planning subnets properly
* Putting everything in one subnet

---

## 📝 Quick MCQs

---

**1. What is a VNet?**
A. Database
B. Private network in Azure
C. Storage account
D. Load balancer

✅ Answer: B

---

**2. What defines the IP range of a VNet?**
A. Subnet
B. Address space
C. NSG
D. Region

✅ Answer: B

---

**3. Why use subnets?**
A. Billing
B. Organization & security
C. Storage
D. DNS

✅ Answer: B

---

**4. Can resources inside a VNet communicate?**
A. No
B. Yes
C. Only internet
D. Only Azure

✅ Answer: B

---
