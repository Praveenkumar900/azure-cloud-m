“Before we build networks in Azure, we need to understand how the internet actually works.”

👉 “Every app, every website, every cloud service depends on these concepts.”

---

# 🌍 1. IP Addressing

“An IP address is a **unique identifier** for a device on a network.”

👉 Like a **home address for your computer**

---

## 📦 Example

* `192.168.1.10` → your laptop
* `8.8.8.8` → Google DNS

---

## 📦 Diagram

<img width="272" height="170" alt="image" src="https://github.com/user-attachments/assets/6276f8a5-ed80-4fda-985e-42218a07a97a" />

```
---

## 🧠 Real-Life Example

“When you open a website, your system connects to its IP address behind the scenes.”

---

# 🔢 2. IPv4 vs IPv6

---

### 🔹 IPv4

* 32-bit address
* Format: `192.168.1.1`
* Limited (~4.3 billion addresses)

---

### 🔹 IPv6

* 128-bit address
* Format: `2001:0db8:85a3::8a2e:0370:7334`
* Almost unlimited addresses

---

## 🧠 Analogy

IPv4 = Old phone numbers
IPv6 = Modern unlimited mobile numbers

---

## 🎯 Key Point

👉 “Azure supports both IPv4 and IPv6”

=================================================
---

# 🔢 IP Address Classes (IPv4)

In traditional (classful) addressing, IPv4 addresses are divided into **5 classes: A, B, C, D, E**

---

## 🅰️ Class A

* **Range:** `1.0.0.0 → 126.255.255.255`
* **Default Subnet Mask:** `255.0.0.0` (/8)
* **First Octet Range:** 1–126

### 🧠 Use Case:

* Very large organizations
* Example: Large enterprises, ISPs

### 📦 Capacity:

* ~16 million hosts per network

---

## 🅱️ Class B

* **Range:** `128.0.0.0 → 191.255.255.255`
* **Default Subnet Mask:** `255.255.0.0` (/16)
* **First Octet Range:** 128–191

### 🧠 Use Case:

* Medium-sized organizations
* Example: Universities, large companies

### 📦 Capacity:

* ~65,000 hosts per network

---

## 🅲 Class C

* **Range:** `192.0.0.0 → 223.255.255.255`
* **Default Subnet Mask:** `255.255.255.0` (/24)
* **First Octet Range:** 192–223

### 🧠 Use Case:

* Small networks
* Example: Offices, homes

### 📦 Capacity:

* 254 hosts per network

---

## 🅳 Class D

* **Range:** `224.0.0.0 → 239.255.255.255`

### 🧠 Use Case:

* **Multicast** (one-to-many communication)
  👉 Example: Live video streaming

---

## 🅴 Class E

* **Range:** `240.0.0.0 → 255.255.255.255`

### 🧠 Use Case:

* Reserved for **research and experimental use**

---

# 📊 Quick Summary Table

| Class | Range   | Default Mask | Use Case            |
| ----- | ------- | ------------ | ------------------- |
| A     | 1–126   | /8           | Very large networks |
| B     | 128–191 | /16          | Medium networks     |
| C     | 192–223 | /24          | Small networks      |
| D     | 224–239 | N/A          | Multicast           |
| E     | 240–255 | N/A          | Experimental        |

---

“Today, we mostly use **CIDR instead of classes**.”

👉 “Which class would your home WiFi fall under?”

(answer: **Class C**)

=================================================

# 📏 3. CIDR (Classless Inter-Domain Routing)

---

“CIDR defines **how many IPs are in a network**.”

---

## 📦 Example

`192.168.1.0/24`

* `/24` → 24 bits fixed
* Remaining bits → available for devices

👉 Total IPs = 256

---

## 📦 Diagram

<img width="255" height="184" alt="image" src="https://github.com/user-attachments/assets/c4adb3d8-98cf-4bbf-b0a0-90b0ccda61ef" />

---

## 🧠 Real-Life Example

“When creating a VNet in Azure, you define CIDR range.”

===============================================================
VNET
===============================================================

# 🧱 4. Subnetting

---

## 🗣️ Explanation

“Subnetting means dividing a network into smaller networks.”

---

## 🧠 Analogy

Big house → rooms
Network → subnets

---

## 📦 Diagram

```id="subnet1"
192.168.1.0/24
   ├── 192.168.1.0/25
   └── 192.168.1.128/25
```

---

## 🧠 Real-Life Example

In Azure:

* Subnet 1 → Web servers
* Subnet 2 → Databases

👉 Improves security & organization

---

# 🧠 5. OSI Model (Very Important)

---

## 🗣️ Explanation

“OSI model explains how data travels across a network.”

---

## 📦 7 Layers

1. Physical
2. Data Link
3. Network
4. Transport
5. Session
6. Presentation
7. Application

---

## 📦 Diagram

<img width="191" height="327" alt="image" src="https://github.com/user-attachments/assets/0082575e-202f-4612-bc2a-77c5b8aa2b29" />
---

## 🧠 Real-Life Example

“When you open a website:

* Application → browser
* Transport → TCP
* Network → IP routing”

---

# 🌐 6. DNS (Domain Name System)

---

“DNS converts **domain names into IP addresses**.”

---

## 🧠 Example

👉 You type: `google.com`
👉 DNS returns: `142.250.x.x`

---

## 📦 Diagram

<img width="364" height="213" alt="image" src="https://github.com/user-attachments/assets/118cf8ca-8e62-4a62-80f5-148397baff4a" />
---

## 🧠 Analogy

DNS = Phonebook
Name → Phone number

---

# 🔍 7. DNS Resolution (Step-by-Step)

---

## 🗣️ Explanation

“How DNS actually works behind the scenes”
---

## 🧠 Simple Explanation

* First check cache
* If not found → ask DNS servers
* Finally → get IP

---

## 🧠 Real-Life Example

“This entire process happens in milliseconds.”

---

# 🔄 8. NAT (Network Address Translation)

---

“NAT allows private IPs to access the internet using a public IP.”

---

## 🧠 Example

Home network:

* Laptop → `192.168.1.10`
* Public IP → `49.x.x.x`

---

## 📦 Diagram

<img width="344" height="135" alt="image" src="https://github.com/user-attachments/assets/7957fdb2-7a4a-4c22-939b-40745983598f" />

---

## 🎯 Why Important?

👉 Saves IP addresses
👉 Used heavily in Azure VNets

---

# ⚖️ 9. Load Balancer

---

“A load balancer distributes traffic across multiple servers.”

---

## 🧠 Real-Life Example

Netflix:

* Millions of users
* Traffic spread across servers

---

## 📦 Diagram

<img width="279" height="198" alt="image" src="https://github.com/user-attachments/assets/8cdf02aa-7b04-4e3b-b795-59d4c94e0851" />
---

## 🎯 Benefits

* High availability
* Better performance
* Fault tolerance

---

# 🔗 10. TCP vs UDP

---

## 🗣️ Explanation

“These are protocols used for communication.”

---

## 🔹 TCP (Transmission Control Protocol)

* Reliable
* Ordered
* Slower

👉 Example:

* Web browsing
* Email

---

## 🔹 UDP (User Datagram Protocol)

* Fast
* No guarantee
* Lightweight

👉 Example:

* Video streaming
* Online gaming
---

## 🧠 Analogy

TCP = Registered courier 📦
UDP = Normal post 📬

---

# 🧠 Putting It All Together

---

# 📝 MCQs

---

## 1. What does DNS do?

A. Stores data
B. Converts domain to IP
C. Encrypts data
D. Routes traffic

✅ Answer: B

---

## 2. Which protocol is reliable?

A. UDP
B. TCP
C. IP
D. DNS

✅ Answer: B

---

## 3. CIDR `/24` means:

A. 24 IPs
B. 256 IPs
C. 128 IPs
D. Unlimited

✅ Answer: B

---

## 4. NAT is used for:

A. Storage
B. Security only
C. IP translation
D. DNS

✅ Answer: C

---

## 5. Load balancer does:

A. Stores data
B. Distributes traffic
C. Encrypts
D. Routes DNS

✅ Answer: B

---

## 6. IPv6 is:

A. Smaller than IPv4
B. Same as IPv4
C. Larger address space
D. Deprecated

✅ Answer: C

---
