# 🌐 AUTO-SCALING-WITH-LOAD-BALANCER

🚀 **AWS Auto Scaling with Load Balancer, Target Group, Launch Template & AMI**  
Achieve **high availability**, **fault tolerance**, and **scalability** by automating EC2 instance management using AWS services.  
Author: **Prasad** 👨‍💻  

---

## 🧭 Project Overview

This project demonstrates **Auto Scaling** with a **Load Balancer** in AWS.  
Using a **Launch Template**, a **custom AMI**, and a **Target Group**, this setup ensures that your application can handle variable traffic loads efficiently without manual intervention.

---

## ⚙️ Architecture Components

| Component | Description |
|------------|-------------|
| **EC2 Instance** | Virtual server used as the base to create AMI. |
| **AMI (Amazon Machine Image)** | Custom image of EC2 used for launching identical instances. |
| **Launch Template** | Blueprint that defines EC2 configurations for Auto Scaling. |
| **Target Group** | Distributes traffic among healthy instances. |
| **Application Load Balancer (ALB)** | Routes requests evenly to EC2 instances across Availability Zones. |
| **Auto Scaling Group (ASG)** | Automatically scales instances up or down based on demand. |

---

## 🚀 Step-by-Step Implementation

### **1️⃣ Launch EC2 Instance**
- Use **Ubuntu** as the base OS.  
- Install your web server (e.g., Nginx/Apache) and deploy your application.  
- Test it in the browser using the public IP.

### **2️⃣ Create AMI (Amazon Machine Image)**
- Stop the instance (optional).  
- Create an **AMI** from the configured EC2 instance.  
- This image will be used in your Launch Template.

### **3️⃣ Create Launch Template**
- Go to **EC2 → Launch Templates → Create Template**.  
- Select the newly created **AMI**.  
- Configure instance type, security groups, and user data if required.

### **4️⃣ Create Target Group**
- Navigate to **EC2 → Target Groups → Create Target Group**.  
- Select **Instances** as the target type.  
- Set health check path (e.g., `/`).

### **5️⃣ Create Application Load Balancer (ALB)**
- Go to **EC2 → Load Balancers → Create Load Balancer**.  
- Choose **Application Load Balancer**.  
- Attach your **Target Group** under listener rules.  
- ALB distributes traffic to healthy instances automatically.

### **6️⃣ Create Auto Scaling Group (ASG)**
- Go to **EC2 → Auto Scaling Groups → Create Auto Scaling Group**.  
- Use the **Launch Template** created earlier.  
- Attach the **Target Group**.  
- Configure **Desired**, **Minimum**, and **Maximum** instance counts.  
- Add scaling policies (e.g., CPU utilization threshold).

---

## 📊 Example Scaling Policy

| Metric | Threshold | Action |
|--------|------------|--------|
| **CPU Utilization > 70%** | Scale Out | +1 Instance |
| **CPU Utilization < 30%** | Scale In | -1 Instance |

---

## 🧩 Testing the Setup
1. Access your **ALB DNS name** in the browser — it should load your web app.  
2. Generate traffic (e.g., using Apache Benchmark or stress tools).  
3. Monitor Auto Scaling Group activity — new instances should launch automatically.  
4. When traffic decreases, instances terminate automatically.

---

## 📁 Folder Structure

AUTO-SCALING-WITH-LOAD-BALANCER/
│
├── images/ # Screenshots of setup & results
└── README.md # Project documentation

---

## 💡 Learning Outcomes

✅ Understand AWS Auto Scaling concepts  
✅ Learn to create and use Launch Templates  
✅ Implement Target Group & ALB integration  
✅ Achieve high availability and fault tolerance  
✅ Monitor and test dynamic scaling in real time

---

## 🖼️ Example Architecture Diagram

       ┌──────────────────────────────┐
       │     Application Load Balancer │
       └──────────────┬───────────────┘
                      │
        ┌─────────────┴──────────────┐
        │        Target Group         │
        └─────────────┬──────────────┘
                      │
       ┌──────────────┴──────────────┐
       │  Auto Scaling Group (ASG)   │
       │   ┌──────────┐  ┌──────────┐│
       │   │ EC2 #1   │  │ EC2 #2   ││
       │   └──────────┘  └──────────┘│
       └──────────────────────────────┘

---

## 🧠 Key Takeaways

- 💥 Auto Scaling optimizes performance and cost.  
- 🌍 Load Balancer ensures zero downtime.  
- ⚙️ Launch Template & AMI standardize configuration.  
- 📈 Target Group monitors instance health.  

---

## 👨‍💻 Author
**Prasad**  
*Cloud & DevOps Enthusiast* ☁️  
📎 [LinkedIn](http://linkedin.com/in/prasad-bhoite-a38a64223)

---

## 📜 License
This project is licensed under the **MIT License**.

---

⭐ *If you like this project, give it a star on GitHub!* 🌟
