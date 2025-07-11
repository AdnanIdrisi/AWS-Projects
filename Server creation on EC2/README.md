<p align="center">
  <img src="Screenshots/awslinuxlogo.webp" width="120"/>
</p>

<h1 align="center" style="color:#2E86C1;">AWS EC2 - Linux Server Creation And Web Hosting</h1>
</br>




<h3 align="left" style="color:#2E86C1;">📝 Introduction</h3>

---

This guide walks you through creating a **Linux server** on AWS EC2 using the AWS Management Console and web hosting on the server. Steps include launching the server, configuring networking, and ensuring secure access.

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
  <img src="Screenshots/step-5b.png" width="600"/>
  <br/>
  <img src="Screenshots/step-5c.png" width="600"/>
  <br/>
  <img src="Screenshots/step-5d.png" width="600"/>
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

### 📌 Step 8: Connecting to server
- Select the server
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
    <img src="Screenshots/step-9c.png" width="600"/>
    <br/>
    <i>Figure 9: Installing packages on linux</i>
</p>

---

### 📌 Step 10: Hosting web page
- Navigate to **C-drive** by `cd /` 
- List all folders by `ls`
- Navigate to **"html"** folder by `cd var/www/html`
- Create an **"index.html"** file by `cat > index.html` and write your content
- Press `Enter` and save your file by `Control + d`

<p align="center">
    <img src="Screenshots/step-10.png" width="600"/>
    <br/>
    <i>Figure 10: Hosting the file</i>
</p>

---

### 📌 Step 11: View the page
- Copy the **Public IP** of the server 
- Search **Public IP** in the browser

<p align="center">
    <img src="Screenshots/step-11.png" width="600"/>
    <br/>
    <img src="Screenshots/step-11b.png" width="600"/>
    <br/>
    <i>Figure 11: Viewing the hosted page</i>
</p>
<br/>

## 📚 Learnings

- Step-by-step EC2 setup
- Key pair login and instance type configuration
- Opened networking ports for real-world hosting
- Configuring Linux machine and installing packages
- Creating file and web hosting

<br/>

## 🔗 Resources

- [AWS EC2 Documentation](https://docs.aws.amazon.com/ec2/)
- [AWS Free Tier](https://aws.amazon.com/free)