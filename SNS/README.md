<p align="center">
  <img src="Screenshots/awslinuxlogo.webp" width="120"/>
</p>

<h1 align="center" style="color:#2E86C1;">AWS SNS – Simple Notification Service Guide</h1>
</br>

<h3 align="left" style="color:#2E86C1;">📝 Introduction</h3>

---

**Amazon Simple Notification Service (SNS)** is a **fully managed messaging service** used to send:

- **SMS (Text Messages)**
- **Emails**
- **Push Notifications**
- **Messages to HTTP/HTTPS endpoints**
- **Messages to AWS Lambda functions or SQS queues**

It is commonly used for **alerts, notifications, and system-to-system messaging**.

---

<h3 align="left" style="color:#2E86C1;">📦 SNS Messaging Types</h3>

---

### ✅ **1️⃣ A2P – Application to Person**

- Sends **notifications from applications to people**  
- **Common Uses:**
  - SMS alerts  
  - Email notifications  
  - OTP verifications  
- **Example in this guide:** Sending SMS from AWS SNS to your mobile phone.

---

### ✅ **2️⃣ A2A – Application to Application**

- Sends **messages between systems or services**  
- **Common Uses:**
  - Triggering AWS Lambda  
  - Sending data to SQS queues  
  - Webhooks to HTTP/HTTPS endpoints  
- **Example Use Case:** Triggering an event-driven workflow in AWS.

---

### 🔍 **Summary Table**

| **Type** | **Purpose** | **Example** |
|----------|-------------|-------------|
| **A2P** | Notify people | SMS, Email |
| **A2A** | Notify applications | Lambda, SQS, HTTP |

---
<br>

<h3 align="left" style="color:#2E86C1;">🧭 Step-by-Step SNS Setup</h3>

---

### 📌 **Step 1: Open SNS in AWS Console**

- Go to **AWS Console**
- In the **search bar**, type **SNS** and select **Simple Notification Service**

<p align="center">
    <img src="Screenshots/step-1.png" width="600"/>
    <br/>
    <i>Figure 1: SNS console</i>
</p>

---

### 📌 **Step 2: Create a Topic**

- Click on **Create Topic**
- **Select Topic Type:**  
  - **Standard** (For SMS & Email)  
  - **FIFO** (For strict message ordering – not used here)

#### **For this guide, select:**  
`Standard Topic`

- **Topic Name:** Example: `topic-1`  
- **Display Name (for SMS):** Example: `my-topic`

<p align="center">
    <img src="Screenshots/step-2.png" width="600"/>
    <br/>
    <img src="Screenshots/step-2b.png" width="600"/>
    <br/>
    <i>Figure 2: Topic Creation</i>
</p>

---

### 📌 **Step 3: Finalize Topic Creation**

- Skip optional settings or configure them as per need  
- Click **Create Topic**

<p align="center">
    <img src="Screenshots/step-3.png" width="600"/>
    <br/>
    <i>Figure 3: Topic creation</i>
</p>

---

### 📌 **Step 4: Create a Subscription**

- Click on your created **Topic**
- Click on **Create Subscription**

#### **Subscription Settings:**

- **Topic ARN:** Auto-selected  
- **Protocol:** `Email`
- **Endpoint:** Enter the email address
- Click on **Create subscription**

<p align="center">
    <img src="Screenshots/step-4.png" width="600"/>
    <br/>
    <img src="Screenshots/step-4b.png" width="600"/>
    <br/>
    <img src="Screenshots/step-4c.png" width="600"/>
    <br/>
    <img src="Screenshots/step-4d.png" width="600"/>
    <br/>
    <i>Figure 4: Creating subscription</i>
</p>

---

### 📌 **Step 5: Verify Email Address**

Since AWS SNS requires verification:

- Open the mail received on the email address from AWS
- Click on **Confirm subscription**
- In **Subscription** section the **Status** will show as **Confirmed**

<p align="center">
    <img src="Screenshots/step-5.png" width="600"/>
    <br/>
    <img src="Screenshots/step-5b.png" width="600"/>
    <br/>
    <i>Figure 5: Verifying Email</i>
</p>

---

### 📌 **Step 6: Publish a Message**

- Go to your **SNS Topic**  
- Click on **Publish Message**
- Enter the **Subject**
- In **Message body** write your message
- Click on **Publish message**
<p align="center">
    <img src="Screenshots/step-6.png" width="600"/>
    <br/>
    <img src="Screenshots/step-6b.png" width="600"/>
    <br/>
    <img src="Screenshots/step-6c.png" width="600"/>
    <br/>
    <img src="Screenshots/step-6d.png" width="600"/>
    <br/>
    <i>Figure 6: Publishing message</i>
</p>

---

<h3 align="left" style="color:#2E86C1;">✅ Final Output</h3>

---

- Check your **Email**.  
- You will receive the **Email notification** from AWS SNS.

<p align="center">
    <img src="Screenshots/step-7.png" width="600"/>
    <br/>
    <i>Figure 7: Result</i>
</p>

---

<h3 align="left" style="color:#2E86C1;">📚 Learnings</h3>

---

- Difference between **A2P and A2A messaging**  
- How to create a **Standard SNS Topic**  
- How to add **Email**  
- How to **send Email notifications** using SNS

---

## 🔗 Resources

- [AWS SNS Documentation](https://docs.aws.amazon.com/sns/latest/dg/welcome.html)  
- [AWS Free Tier](https://aws.amazon.com/free)
