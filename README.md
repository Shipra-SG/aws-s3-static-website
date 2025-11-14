# 🚀 Static Website Hosting on AWS S3 + CloudFront  
This repository contains a fully deployed **static website** hosted on **Amazon S3** and served globally through **CloudFront CDN**.  
It demonstrates core AWS concepts including storage, security, caching, and performance optimization.

---

## 🧩 Table of Contents
- [📌 Project Overview](#-project-overview)
- [🏗️ Architecture](#️-architecture)
- [📁 Folder Structure](#-folder-structure)
- [🚀 How to Deploy](#-how-to-deploy)
- [🌐 Website Output](#-website-output)
- [📚 Concepts Learned](#-concepts-learned)
- [🚀 Future Enhancements](#-future-enhancements)
- [👤 Author](#-author)

---

## 📌 Project Overview
A lightweight static site built using **HTML, CSS, JS**, uploaded to **S3**, and accelerated globally using **CloudFront**.  
This is part of my **AWS + DevOps learning roadmap** to master cloud fundamentals.

### 🎯 Key Features
- S3 Static Website Hosting  
- Public Read Access (Bucket Policy)  
- Global Distribution via CloudFront  
- HTTPS (via CloudFront Redirect)  
- Edge Caching + Invalidation  
- Clean folder structure for GitHub  

---

## 🏗️ Architecture

```
User → CloudFront CDN → S3 Static Website → Objects → Response Cached Globally
```

![Architecture](architecture/architecture-diagram.png)

---

## 📁 Folder Structure

```
aws-s3-static-website/
│
├── src/
│   ├── index.html
│   ├── style.css
│   └── script.js
│
├── architecture/
│   └── architecture-diagram.png
│
├── screenshots/
│   ├── s3-bucket-settings.png
│   ├── cloudfront-distribution.png
│   ├── website-working.png
│
└── README.md
```

---

## 🚀 How to Deploy

### **1️⃣ Create S3 Bucket**
- Disable "Block all public access"  
- Enable static website hosting  
- Upload `index.html`, `style.css`, `script.js`

### **2️⃣ Bucket Policy**
```json
{
  "Version": "2012-10-17",
  "Statement": [{
    "Effect": "Allow",
    "Principal": "*",
    "Action": "s3:GetObject",
    "Resource": "arn:aws:s3:::my-static-site/*"
  }]
}
```

### **3️⃣ Create CloudFront Distribution**
- Origin: S3 Website Endpoint  
- Viewer Protocol: Redirect HTTP → HTTPS  
- Copy distribution URL:  
  ```
  https://d23apl10l24y6s.cloudfront.net/
  ```

### **4️⃣ Cache Invalidation**
```
/*
```

---

## 🌐 Website Output  
(Add screenshots)

| Step | Screenshot |
|------|------------|
| S3 Bucket Settings | ![](screenshots/s3-bucket-settings.png) |
| CloudFront Distribution | ![](screenshots/cloudfront-distribution.png) |
| Live Website | ![](screenshots/website-working.png) |

---

## 📚 Concepts Learned

### 🟡 **S3**
- Object storage  
- Static website hosting  
- Bucket policies  
- Public access control  

### 🟣 **CloudFront**
- CDN  
- Edge caching  
- Cache invalidation  
- HTTPS redirect  

### 🔵 **General AWS**
- Regions & endpoints  
- Storage class basics  
- IAM public access principles  

---

## 🚀 Future Enhancements
- Add custom domain using Route53  
- Use AWS Certificate Manager for full HTTPS  
- Add CI/CD deployment with GitHub Actions  
- Add logs monitoring & analytics (CloudWatch)  

---

## 👤 Author
**Shipra**  
AWS | Cloud | DevOps Learner  
⭐ *Always learning. Always building.*


