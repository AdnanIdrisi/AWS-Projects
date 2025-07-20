<p align="center">
  <img src="Screenshots/awslinuxlogo.webp" width="120"/>
</p>

<h1 align="center" style="color:#2E86C1;">AWS SQS – Simple Queue Service Guide</h1>
</br>

<h3 align="left" style="color:#2E86C1;">📝 Introduction</h3>

---

**Amazon SQS (Simple Queue Service)** is a **fully managed message queuing service** that helps decouple components of distributed systems.

### ✅ **Why Use SQS?**

- Store and manage **messages between services**  
- Handle **asynchronous communication**  
- Prevent **message loss and duplication**  
- **Scales automatically**

---

<h3 align="left" style="color:#2E86C1;">📦 SQS Types</h3>

---

### **1️⃣ Standard Queue**

- **High throughput**  
- **At-least-once delivery**  
- **Possible duplicates**  
- **Best-effort ordering**

### **2️⃣ FIFO Queue (First-In-First-Out)**

- **Exact message ordering**  
- **Exactly-once delivery**  
- **Limited throughput compared to Standard**

---
<br>
<h3 align="left" style="color:#2E86C1;">🧭 Step-by-Step SQS Setup</h3>

---

### 📌 **Step 1: Open SQS in AWS Console**

- Go to **AWS Console**  
- Search for **SQS** in the search bar  
- Click **Create Queue**

<p align="center">
    <img src="Screenshots/step-1.png" width="600"/>
    <br/>
</p>

---

### 📌 **Step 2: Configure Queue**

- **Type:**  
  - **Standard** or **FIFO** (choose based on requirement)

#### **Queue Settings:**

- **Queue Name:** Example: `my-queue.fifo`  
- **Configuration:** Leave default or adjust as needed  
- **Encryption:** No changes required (default AES256)  
- **Access Policy:** Only queue owner can access  
- **Retrieval Policy:** Disabled  
- **Dead Letter Queue:** Disabled (optional)
- Click on **Create queue**

<p align="center">
  <img src="Screenshots/step-2.png" width="600"/>
  <br>
  <img src="Screenshots/step-2b.png" width="600"/>
  <br>
</p>

---

### 📌 **Step 3: Create SNS Topic**

- Go to **SNS Dashboard**  
- Click **Create Topic**  
- **Type:** FIFO  
- **Name:** Example: `my-sns-topic.fifo`
- Click **Create topic**

<p align="center">
    <img src="Screenshots/step-3.png" width="600"/>
    <br/>
    <img src="Screenshots/step-3b.png" width="600"/>
    <br/>
    <img src="Screenshots/step-3c.png" width="600"/>
    <br/>
    <i>Figure 1: SNS console</i>
</p>

---

### 📌 **Step 4: Create Subscription**

- **Protocol:** `SQS`  
- **Endpoint:** Select the **SQS Queue** you just created  
- Click **Create Subscription**

<p align="center">
    <img src="Screenshots/step-4.png" width="600"/>
    <br/>
    <img src="Screenshots/step-4b.png" width="600"/>
    <br/>
    <img src="Screenshots/step-4c.png" width="600"/>
    <br/>
</p>

---

### 📌 **Step 5: Publish a Message from SNS**

- Go to **SNS Topics**  
- Select your **FIFO topic**  
- Click **Publish Message**

#### **Fill the form:**

- **Subject:** Example: `AWS SQS Message`  
- **Message Group ID:** (Required for FIFO) – Example: `101`  
- **Deduplication ID:** (Optional, or auto-generated) - Example: `102`
- **Time To Live (TTL):**  
  - The **lifetime of a message in seconds**  
  - If TTL expires, the message will not be delivered  
- **Message Body:** Your message content
- Click **Publish message**

<p align="center">
    <img src="Screenshots/step-5.png" width="600"/>
    <br/>
    <img src="Screenshots/step-5b.png" width="600"/>
    <br/>
    <img src="Screenshots/step-5c.png" width="600"/>
    <br/>
    <img src="Screenshots/step-5d.png" width="600"/>
    <br/>
</p>

---

### 📌 **Step 6: Check Messages in SQS**

- Go to your **SQS Queue**  
- You will see the **Message Available count increase**

<p align="center">
    <img src="Screenshots/step-6.png" width="600"/>
    <br/>
</p>

---

### 🔄 **Test Multiple Messages**

- **Publish multiple messages** (2-3 times)  
- Check the **message count** in your SQS Queue.  
- Each message will be stored in the queue for consumers to process.

<p align="center">
    <img src="Screenshots/step-7.png" width="600"/>
    <br/>
</p>

---

<h3 align="left" style="color:#2E86C1;">📚 Learnings</h3>

---

- How to create **FIFO and Standard Queues**  
- How to connect **SNS to SQS**  
- How to **send and retrieve messages from SQS**  
- How **Time To Live (TTL)** works in message handling

---

## 🔗 Resources

- [AWS SQS Documentation](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html)  
- [AWS Free Tier](https://aws.amazon.com/free)
