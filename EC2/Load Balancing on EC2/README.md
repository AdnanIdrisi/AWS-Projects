<p align="center">
  <img src="Screenshots/awslinuxlogo.webp" width="120"/>
</p>

<h1 align="center" style="color:#2E86C1;">AWS EC2 - Load Balancing in EC2</h1>
</br>




<h3 align="left" style="color:#2E86C1;">📝 Introduction</h3>

---

This guide walks you through creating multiple **Linux server** on AWS EC2 using the AWS Management Console and applying load balancing on the server to distribute the incoming network traffic. Steps include launching the server, creating load balancer and viewing result.

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
- Example name: `my-server`

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
- Click on **"Edit"**
- Click on **"Add security group rule"**
- Select **"All trafic"** in **"Type"**
- Select **"Anywhere"** in **"Source type"**

<p align="center">
  <img src="Screenshots/step-6.png" width="600"/>
  <br/>
  <img src="Screenshots/step-6b.png" width="600"/>
  <br/>
  <i>Figure 6: Opening ports in the security group</i>
</p>

---

### 📌 Step 7: Launch the Instance
- Enter the number of Instance you want
- Click **“Launch Instance”**
- Wait until the status is **"running"**

<p align="center">
  <img src="Screenshots/step-7.png" width="600"/>
  <br/>
  <i>Figure 7: Launching the EC2 instance</i>
</p>

---

### 📌 Step 8: Connecting to server
- Select each server one by one and perform Step-8 to Step-10
- Click on **“Connect”**
- In the **"EC2 Instance Connect"** click on **"Connect"**

<p align="center">
    <img src="Screenshots/step-8.png" width="600"/>
    <br/>
    <img src="Screenshots/step-8b.png" width="600"/>
    <br/>
    <i>Figure 8: Connecting the EC2 instance</i>
</p>

---

### 📌 Step 9: Installing Packages
- Gain root access by `sudo su`
- Update server by `yum update -y`
- Install package by `yum install httpd -y`
- Activate package by `systemctl start httpd`

<p align="center">
    <img src="Screenshots/step-9.png" width="600"/>
    <br/>
    <img src="Screenshots/step-9b.png" width="600"/>
    <br/>
    <i>Figure 9: Installing packages on linux</i>
</p>

---

### 📌 Step 10: Hosting web page
- Navigate to **C-drive** by `cd /` 
- List all folders by `ls`
- Navigate to **"html"** folder by `cd var/www/html`
- Create an **"index.html"** file by `cat > index.html` 
- Write different content in different servers
- Press `Enter` and save your file by `Control + d`

<p align="center">
    <img src="Screenshots/step-10.png" width="600"/>
    <br/>
    <img src="Screenshots/step-10b.png" width="600"/>
    <br/>
    <img src="Screenshots/step-10c.png" width="600"/>
    <br/>
    <i>Figure 10: Hosting the file</i>
</p>

---

### 📌 Step 11: Create Load balancer
- Click on **"Load Balancer"**
- Click on **"Create load Balancer"**
- In **"Application Load Balancer"** click on **"Create"**
- Give **"Load balancer"** name
- Select **"Internet-facing"** in **"Scheme"**
- Select multiple security groups (3 or 4)

<p align="center">
    <img src="Screenshots/step-11.png" width="600"/>
    <br/>
    <img src="Screenshots/step-11b.png" width="600"/>
    <br/>
    <img src="Screenshots/step-11c.png" width="600"/>
    <br/>
    <img src="Screenshots/step-11d.png" width="600"/>
    <br/>
    <i>Figure 11: Creating load balancer group</i>
</p>

---

### 📌 Step 12: Create target group
- In **"Listeners and routing"** click on **"Create target group"**
- Select **"Instance"** in **"target type"**
- Give the name of **"Target group"**
- Click on **"Next"**
- Select all the created instance and click on **"Include as pending below"**
- Click on **"Create target group"**


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
    <i>Figure 12: Creating target group</i>
</p>

---

### 📌 Step 13: Launch load balancer
- Click on the refresh icon
- Select your previous created target group
- Click on **"Create load balancer"**
- Wait until the **"Status"** shows **"Active"**

<p align="center">
    <img src="Screenshots/step-13.png" width="600"/>
    <br/>
    <img src="Screenshots/step-13b.png" width="600"/>
    <br/>
    <img src="Screenshots/step-13c.png" width="600"/>
    <br/>
    <i>Figure 13: Launching load balancer</i>
</p>

---

### 📌 Step 14: Preview result
- Copy the **"DNS name** and open it in new tab
- Refresh the tab multiple times and the request will go to different servers each time


<p align="center">
    <img src="Screenshots/step-14.png" width="600"/>
    <br/>
    <img src="Screenshots/step-14b.png" width="600"/>
    <br/>
    <img src="Screenshots/step-14c.png" width="600"/>
    <br/>
    <i>Figure 14: Showing results</i>
</p>
<br/>

## 📚 Learnings

- Step-by-step EC2 setup
- Step-by-step creation of load balancer
- Step-by-step creation of target group

<br/>

## 🔗 Resources

- [AWS Load Balancer Documentation](https://docs.aws.amazon.com/elasticloadbalancing/)
- [AWS Free Tier](https://aws.amazon.com/free)