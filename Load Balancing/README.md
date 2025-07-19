<p align="center">
  <img src="Screenshots/awslinuxlogo.webp" width="120"/>
</p>

<h1 align="center" style="color:#2E86C1;">AWS EC2 - Load Balancing in EC2</h1>
</br>




<h3 align="left" style="color:#2E86C1;">📝 Introduction</h3>

---

This guide walks you through creating a **Linux server** on AWS EC2 using the AWS Management Console and applying auto scaling on the server. Steps include launching the server, creating auto scaling group.

</br>

<h3 align="left" style="color:#2E86C1;">🧭 Step-by-Step Instructions</h3>

---

### 📌 Step 1: Search EC2 and Click "Launch Instance"
- Go to the AWS Console
- Search for **EC2**
- Click on **"Launch Instance"**

<p align="center">
  <img src="Screenshots/step-1.png" width="600"/>
  <br/>
  <i>Figure 1: Launch EC2 from AWS Console</i>
</p>

---

### 📌 Step 2: Provide a Name for Your Server
- Example name: `my-linux-server`

<p align="center">
  <img src="Screenshots/step-2.png" width="600"/>
  <br/>
  <i>Figure 2: Naming the EC2 instance</i>
</p>

---

### 📌 Step 3: Choose the Operating System
- Choose from:
  - ✅ Amazon Linux
  - ✅ Ubuntu
  - ✅ (Optional: Windows or Android)

<p align="center">
  <img src="Screenshots/step-3.png" width="600"/>
  <br/>
  <i>Figure 3: Selecting an OS (e.g. Linux)</i>
</p>

---

### 📌 Step 4: Select Instance Type
- Use **t2.micro** (Free Tier eligible)
- Consider your app’s CPU, memory, and network needs

<p align="center">
  <img src="Screenshots/step-4.png" width="600"/>
  <br/>
  <i>Figure 4: Selecting the instance type</i>
</p>

---

### 📌 Step 5: Configure Key Pair Login
- Select or create a **key pair**
- Download the `.pem` file for secure SSH access

<p align="center">
  <img src="Screenshots/step-5.png" width="600"/>
  <br/>
  <i>Figure 5: Key pair setup for EC2 login</i>
</p>

---

### 📌 Step 6: Configure Network Settings
- Allow:
  - ✅ SSH (Port 22)
  - ✅ HTTP (Port 80)
  - ✅ HTTPS (Port 443)

<p align="center">
  <img src="Screenshots/step-6.png" width="600"/>
  <br/>
  <i>Figure 6: Opening ports in the security group</i>
</p>

---

### 📌 Step 7: Launch the Instance
- Click **“Launch Instance”**
- Wait until the status is **"running"**

<p align="center">
  <img src="Screenshots/step-7.png" width="600"/>
  <br/>
  <img src="Screenshots/step-7b.png" width="600"/>
  <br/>
  <i>Figure 7: Launching the EC2 instance</i>
</p>

---

### 📌 Step 8: Create AMI
- Select the server
- Click on **“Action”**
- Click on **“Image and templates”**
- Click on **“Create image”**

<p align="center">
    <img src="Screenshots/step-8.png" width="600"/>
    <br/>
    <i>Figure 8: Creating AMI for auto scaling</i>
</p>

---

### 📌 Step 9: Launch AMI
- Give a name to the AMI
- Write the description on AMI
- Click on **“Create image”**
- Wait until **"Status"** shows **"Available"**

<p align="center">
    <img src="Screenshots/step-9.png" width="600"/>
    <br/>
    <img src="Screenshots/step-9b.png" width="600"/>
    <br/>
    <img src="Screenshots/step-9c.png" width="600"/>
    <br/>
    <i>Figure 9: Launching the AMI</i>
</p>

---

### 📌 Step 10: Create Auto Scaling Group
- Click on **"Auto Scaling Group"**
- Click on **"Create Auto Scaling Group"**
- Give name to the auto scaling group
- Click on **"Create a launch template"**

<p align="center">
    <img src="Screenshots/step-10.png" width="600"/>
    <br/>
    <img src="Screenshots/step-10b.png" width="600"/>
    <br/>
    <i>Figure 10: Creating auto scaling group</i>
</p>

---

### 📌 Step 11: Create Launch Template
- Give name to the launch template
- Give description of launch template
- Click on **"My AMIs"**
- Select the AMI which you created on above steps
- Select recent created security groups (2 or 3)
- Click on **"Create launch template"**

<p align="center">
    <img src="Screenshots/step-11.png" width="600"/>
    <br/>
    <img src="Screenshots/step-11b.png" width="600"/>
    <br/>
    <img src="Screenshots/step-11c.png" width="600"/>
    <br/>
    <img src="Screenshots/step-11d.png" width="600"/>
    <br/>
    <i>Figure 11: Creating launch template</i>
</p>

---

### 📌 Step 12: Launch Auto Scaling Group
- Click on the refresh icon in launch template
- Select the launch template created in above step and click on **"Next"**
- Select all the availability zones 
- Select **"Balanced best effort"** and click on **"Next"** 
- Again click on **"Next"**
- Give the **"Desired capacity"**, **"Min desired capacity"** and **"Max desired capacity"** and click on **"Next"**
- Again click on **"Next"** two times
- Click on **"Create Auto Scaling group"**

<p align="center">
    <img src="Screenshots/step-12.png" width="600"/>
    <br/>
    <img src="Screenshots/step-12b.png" width="600"/>
    <br/>
    <img src="Screenshots/step-12c.png" width="600"/>
    <br/>
    <img src="Screenshots/step-12d.png" width="600"/>
    <br/>
    <img src="Screenshots/step-12e.png" width="600"/>
    <br/>
    <img src="Screenshots/step-12f.png" width="600"/>
    <br/>
    <img src="Screenshots/step-12g.png" width="600"/>
    <br/>
    <i>Figure 10: Launching auto scaling group</i>
</p>

---

### 📌 Step 13: Preview result
- In the Instance section new servers will be launched by auto scaling group 

<p align="center">
    <img src="Screenshots/step-13.png" width="600"/>
    <br/>
    <i>Figure 11: Showing results</i>
</p>
<br/>

## 📚 Learnings

- Step-by-step EC2 setup
- Step-by-step creation of Auto Scaling Group
- Step-by-step creation of launch template

<br/>

## 🔗 Resources

- [AWS Auto Scaling Documentation](https://docs.aws.amazon.com/autoscaling/)
- [AWS Free Tier](https://aws.amazon.com/free)