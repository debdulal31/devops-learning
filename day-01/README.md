# 🚀 Day 1 — AWS EC2 & SSH Fundamentals

## 🎯 Objective

Understand the basic relationship between:

```text
AWS
 ↓
EC2
 ↓
Ubuntu
 ↓
SSH
```

The goal was to launch a cloud server and understand how remote access works.

---

## ☁️ Topics Learned

### 1. AWS

AWS provides cloud infrastructure and services that can be used to build and operate applications.

---

### 2. Amazon EC2

EC2 provides virtual servers in the AWS cloud.

For this learning journey, an Ubuntu-based EC2 instance is being used as a practice server.

Conceptually:

```text
AWS
└── EC2
    └── Ubuntu Server
```

---

### 3. SSH

SSH (Secure Shell) is used to securely connect to a remote Linux server.

Conceptually:

```text
Local Computer
      │
      │ SSH
      ▼
AWS EC2 Ubuntu Server
```

---

### 4. SSH Key Pair

EC2 uses a key pair for SSH authentication.

The private key is stored locally as a `.pem` file.

```text
Private Key (.pem)
       │
       ▼
      SSH
       │
       ▼
EC2 Ubuntu Server
```

The private key must be protected and must never be committed to GitHub.

---

### 5. Security Groups

A Security Group controls network access to an EC2 instance.

For SSH access, the server needs appropriate access to:

```text
TCP Port 22
```

Conceptually:

```text
Internet
   │
   ▼
Security Group
   │
   │ Port 22
   ▼
EC2 Instance
```

---

### 6. WSL vs EC2

WSL is being used for local Linux practice.

EC2 is being used for cloud/server practice.

```text
Windows
│
└── WSL Ubuntu
     └── Local Linux practice

AWS
│
└── EC2 Ubuntu
     └── Cloud/server practice
```

---

## 🧠 Key Concepts

| Concept | Meaning |
|---|---|
| AWS | Cloud platform |
| EC2 | Virtual cloud server |
| Ubuntu | Linux operating system |
| SSH | Secure remote connection |
| Key Pair | Authentication mechanism |
| `.pem` | Private SSH key file |
| Security Group | Network access control |
| Port 22 | Default SSH port |
| WSL | Linux environment on Windows |

---

## 🔐 Security Notes

Private keys must never be uploaded to GitHub.

Example:

```text
*.pem
*.key
```

should be included in `.gitignore`.

---

## 📌 Day 1 Takeaway

The fundamental architecture learned today:

```text
My Computer
     │
     │ SSH
     ▼
AWS EC2
     │
     ▼
Ubuntu Linux
```

This forms the foundation for learning Linux administration and AWS-based DevOps.

---

## ✅ Status

**Day 1 — Completed**
