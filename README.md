# 🚀 Static Frontend Deployment using AWS (S3 + CloudFront + CodePipeline)

## 📌 Project Overview

This project demonstrates how to deploy a **static frontend website** using AWS services with a complete CI/CD pipeline.

The architecture uses:

* AWS CodePipeline for automation
* Amazon S3 for static hosting
* Amazon CloudFront for CDN (fast delivery)
* Amazon Route 53 for domain management

---

## 🧠 Architecture

```
Developer → GitHub → CodePipeline → S3 → CloudFront → Route53 → User 🌍
```

---

## ⚙️ AWS Services Used

* AWS CodePipeline (CI/CD automation)
* Amazon S3 (Static website hosting)
* Amazon CloudFront (Content Delivery Network)
* Amazon Route 53 (DNS & domain mapping)
* AWS Certificate Manager (SSL/HTTPS)

---

## 🔧 Setup Steps

### 1️⃣ Upload Code to GitHub

* Push your static frontend code (HTML, CSS, JS) to GitHub repository

---

### 2️⃣ Create S3 Bucket

* Enable **Static Website Hosting**
* Set:

  * Index document: `index.html`
  * Error document: `index.html`
* Disable Block Public Access
* Add bucket policy for public read access

---

### 3️⃣ Setup CloudFront

* Create distribution
* Origin: S3 bucket
* Default root object: `index.html`
* Enable HTTPS (via ACM)

---

### 4️⃣ Configure Route 53

* Create hosted zone
* Add **A record (Alias)** → CloudFront distribution

---

### 5️⃣ Create CodePipeline

* Source: GitHub repository
* Build: (Skipped - static project)
* Deploy: S3 bucket
* Enable "Extract files before deploy"

---

## 🔄 CI/CD Workflow

1. Push code to GitHub
2. CodePipeline triggers automatically
3. Files deployed to S3
4. CloudFront serves updated content
5. Website goes live 🌍

---

## ⚠️ Challenges Faced

### ❌ Issue: Changes not reflecting on live site

* Cause: CloudFront caching old files

### ✅ Solution:

* Performed cache invalidation:

```
/*
```

---

## 💡 Key Learnings

* How CI/CD works for static websites
* Difference between S3 and CloudFront
* Importance of caching in CDN
* How to troubleshoot deployment issues
* Domain mapping using Route 53

---

## 🌐 Live Website

👉 https://www.mayurpatil.shop/

---

## 🚀 Future Improvements

* Automate CloudFront cache invalidation
* Use private S3 bucket with Origin Access Control (OAC)
* Add multi-environment deployment (dev/prod)
* Implement versioned deployments

---

## 📷 Screenshots (Optional)

*Add screenshots of pipeline, S3, CloudFront here*

---

## 👨‍💻 Author

Mayur Patil

---

## ⭐ Conclusion

This project showcases a real-world DevOps implementation of deploying a frontend application using AWS with scalability, performance, and automation.

---
