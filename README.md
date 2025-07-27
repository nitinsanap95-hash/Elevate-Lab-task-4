# 🔥 Task 4: Setup and Use a Firewall on Windows/Linux (Cybersecurity Internship)

## 🎯 Objective
Configure and test basic firewall rules to allow or block specific traffic, and understand how firewalls filter network communication.

---

## 🛠 Tools Required
- **Windows Firewall** (GUI based)
- **UFW (Uncomplicated Firewall)** – Linux
- **Netcat (`nc`)** or Telnet for testing connections

---

## ✅ Step-by-Step Instructions

### 🪟 For Windows Users

#### 🔹 Step 1: Open Windows Firewall
1. Press `Win + R`, type `control firewall.cpl`, press Enter.
2. Click **Advanced Settings** → opens **Windows Defender Firewall with Advanced Security**.

#### 🔹 Step 2: Block Inbound Port (e.g., 23 – Telnet)
1. Go to **Inbound Rules > New Rule**.
2. Select **Port** → TCP → Specify port **23**.
3. Choose **Block the connection** → Apply to all profiles.
4. Name rule "Block Telnet Port 23".

📸 Screenshot: `screenshots/block_telnet_windows.png`

#### 🔹 Step 3: Allow Port 22 (SSH)
1. New Rule → Port → TCP → Port **22**.
2. Action → **Allow the connection**.
3. Name rule "Allow SSH 22".

📸 Screenshot: `screenshots/allow_ssh_windows.png`

---

### 🐧 For Linux (Ubuntu/Kali) Users

#### 🔹 Step 1: Enable UFW
```bash
sudo ufw enable
```

#### 🔹 Step 2: List Current Rules
```bash
sudo ufw status verbose
```

#### 🔹 Step 3: Block Port 23 (Telnet)
```bash
sudo ufw deny 23
```

📸 Screenshot: `screenshots/ufw_block_telnet.png`

#### 🔹 Step 4: Allow SSH (Port 22)
```bash
sudo ufw allow 22
```

#### 🔹 Step 5: Test Connection
```bash
nc -zv 127.0.0.1 23
```
You should see **Connection refused** if blocked.

#### 🔹 Step 6: Remove Rule
```bash
sudo ufw delete deny 23
```

📸 Screenshot: `screenshots/ufw_rules_list.png`

---

## 🔍 Key Concepts
- **Firewall**: Filters traffic based on rules (ports, IPs, protocols)
- **Inbound Rule**: Blocks/Allows incoming traffic
- **Outbound Rule**: Controls outgoing connections
- **Stateful Firewall**: Remembers connection state (e.g., replies allowed)
- **Stateless Firewall**: Treats each packet independently
- **NAT (Network Address Translation)**: Hides internal IPs using public IP

---

## ❓ Interview Questions & Answers

### 1. What is a firewall?
A firewall is a network security system that monitors and controls incoming/outgoing traffic based on security rules.

### 2. Difference between stateful and stateless firewalls?
- **Stateful**: Tracks entire session. Allows return traffic automatically.
- **Stateless**: Treats each packet independently without context.

### 3. What are inbound and outbound rules?
- **Inbound**: Controls traffic **to** your system.
- **Outbound**: Controls traffic **from** your system.

### 4. How does UFW simplify firewall management?
UFW provides a simple command-line interface to manage iptables (Linux firewall).

### 5. Why block port 23 (Telnet)?
Telnet is an unencrypted protocol. Attackers can intercept credentials. It’s recommended to use **SSH instead**.

### 6. What are common firewall mistakes?
- Leaving default ports open
- Allowing any IP (`0.0.0.0/0`)
- Not updating rules
- Conflicting rules or misconfiguration

### 7. How does a firewall improve network security?
- Blocks unauthorized access
- Limits exposure of services
- Prevents lateral movement inside networks

### 8. What is NAT in firewalls?
NAT hides internal IP addresses behind a public one, increasing privacy and reducing direct attack surface.

---

## 🗂 GitHub Repo Structure
```
firewall-task/
├── README.md
├── screenshots/
│   ├── block_telnet_windows.png
│   ├── allow_ssh_windows.png
│   ├── ufw_block_telnet.png
│   └── ufw_rules_list.png
```



## ✅ Task Completed By:
**Nitin sanap**  
Cybersecurity Intern
