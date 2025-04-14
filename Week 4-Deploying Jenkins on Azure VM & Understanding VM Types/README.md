# 🚀 Week 4: Deploying Jenkins on Azure VM & Understanding Azure VM Types

Welcome to **Week 4** of our Azure Cloud Series!  
In this session, we focused on deploying **Jenkins** on an **Azure Virtual Machine (VM)** while understanding the fundamentals and types of Azure VMs.  
Whether you're a DevOps enthusiast or a cloud engineer, this week bridges theory and hands-on expertise. 🔧☁️

---

## 📚 What We Covered

### ✅ 1. **Virtualization & Azure VMs**
- **Virtual Machines (VMs)** in Azure are built using a virtualization layer powered by **hypervisors**.
- These hypervisors abstract hardware and allow multiple OS environments to run concurrently.
- Azure offers scalable, flexible VM options with predictable performance and pricing.

---

### ✅ 2. **Choosing the Right Azure VM Type**

Understanding VM types is critical to performance and cost efficiency:

| VM Series | Type                | Use Case Example                               |
|----------|---------------------|------------------------------------------------|
| **D-series** | Memory Optimized    | Databases, in-memory caching, enterprise apps |
| **F-series** | Compute Intensive   | High CPU workloads, batch processing          |
| **N-series** | GPU Accelerated     | AI/ML, video processing, graphics rendering   |

You should select a VM type based on your workload requirements.

---

### ✅ 3. **Hands-On: Deploying Jenkins on Azure VM**

**Steps we followed:**

1. **Create Azure VM**  
   - Chose Ubuntu-based image (e.g. Ubuntu 22.04 LTS)
   - Selected appropriate VM size (e.g. Standard DS1 v2)

2. **Connect via SSH**
   ```bash
   ssh azureuser@<public-ip>
   ```

3. **Update System & Install Java (required by Jenkins)**
   ```bash
   sudo apt update && sudo apt upgrade -y
   sudo apt install openjdk-11-jdk -y
   ```

4. **Add Jenkins Repository & Install**
   ```bash
   curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee \
     /usr/share/keyrings/jenkins-keyring.asc > /dev/null
   echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
     https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
     /etc/apt/sources.list.d/jenkins.list > /dev/null
   sudo apt update
   sudo apt install jenkins -y
   ```

5. **Start & Enable Jenkins**
   ```bash
   sudo systemctl start jenkins
   sudo systemctl enable jenkins
   ```

6. **Access Jenkins on Browser**
   - Open port **8080** in Azure Networking
   - Visit: `http://<VM_PUBLIC_IP>:8080`

---

### ✅ 4. **Networking & Security**

- Configured **Network Security Group (NSG)** to allow ports:
  - **22**: SSH
  - **8080**: Jenkins UI
- Ensured **firewall rules** are in place.
- Applied **minimal privilege** and user restrictions for secure deployment.

---

### ✅ 5. **Auto-scaling with Azure VMSS (VM Scale Sets)**

- **VM Scale Sets** allow you to scale VM instances automatically based on:
  - CPU usage
  - Memory consumption
  - Incoming traffic
- Helps maintain **high availability** and **cost-efficiency**.

---

## 🛠️ Tools Used

- **Azure Portal / Azure CLI**
- **Jenkins (CI/CD tool)**
- **Ubuntu 22.04 LTS**
- **OpenJDK 11**
- **VMSS (Scale Sets)**

---

## 🌐 Outcomes & Learnings

- Understood different VM types and their real-world use cases.
- Successfully deployed Jenkins with proper configuration.
- Learned to manage networking and secure VMs.
- Explored auto-scaling options for production-grade environments.

---

## 🔮 What's Next?

Up next: **More Azure DevOps & Automation**  
We'll be covering topics like:

- Azure DevOps Pipelines
- Infrastructure as Code (IaC) with ARM & Bicep
- Automation using Azure CLI, PowerShell, and GitHub Actions

Stay tuned for Week 5! 💡

---

## 🔗 Connect & Share

If you found this helpful, feel free to:
- 🌟 Star the repository
- 🍴 Fork and use it in your own projects
- 📢 Share it with fellow cloud enthusiasts!

---

## 📌 Hashtags

`#Azure #DevOps #Jenkins #CloudComputing #AzureVM #Automation #Kubernetes #DevOpsJourney`

---

📁 **Repository Structure (Optional)**

```
.
├── README.md
├── scripts
│   └── install-jenkins.sh
├── docs
│   └── vm-types-overview.md
└── screenshots
    └── jenkins-deployment.png
```

---
```
