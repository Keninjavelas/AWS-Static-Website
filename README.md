# ☁️ AWS Static Website Deployment — End-to-End Project (Phases 1–3)

## 📘 Overview

This project demonstrates how to build, host, and monitor a **secure, scalable, and cost-efficient static website** on AWS — all within the **free tier**.
It’s part of a long-term learning journey toward mastering **AWS Cloud Engineering** and building a professional cloud portfolio.

---

## 🏗️ Architecture Summary

| Phase       | Focus                                | AWS Services Used                          | Key Skills                       |
| ----------- | ------------------------------------ | ------------------------------------------ | -------------------------------- |
| **Phase 1** | Hosting a Static Website             | S3, Route53 (optional)                     | Website hosting, bucket policies |
| **Phase 2** | Global Content Delivery & Automation | CloudFront, GitHub Actions, IAM            | CDN, HTTPS, CI/CD pipeline       |
| **Phase 3** | Monitoring & Resiliency              | CloudFront Logs, S3 Versioning, CloudWatch | Logging, versioning, metrics     |

---

# 🧩 Phase 3 — Monitoring, Logging & Versioning

## 📊 Overview

Phase 3 introduces observability and resiliency to our AWS static website architecture.
We’ve added **CloudFront access logging**, **S3 versioning**, and **metrics monitoring** to ensure visibility, traceability, and recovery capabilities.

---

## ⚙️ Features Implemented

### **1️⃣ CloudFront Access Logging**

* Created a dedicated **log bucket** (`my-first-aws-site-logs`) for storing access logs.
* Configured a **Standard Log Destination** in CloudFront to deliver `.gz` log files automatically to the log bucket.
* Added optional log prefix: `cloudfront-logs/`
* Disabled **Real-Time Logs** (paid feature) to stay within free-tier limits.

**Result:**
Traffic and request data are now recorded in the logs bucket for analysis and audits.

---

### **2️⃣ S3 Versioning**

Enabled versioning for both S3 buckets:

* ✅ `my-first-aws-site-aryan` (main static website)
* ✅ `my-first-aws-site-logs` (log storage)

**Benefit:**
Every object change is preserved as a new version.
You can restore previous versions of files if they’re accidentally modified or deleted.

---

### **3️⃣ Monitoring & Metrics**

* Accessed **CloudFront → Monitoring tab** to view metrics such as:

  * Requests count
  * Data transferred
  * 4xx/5xx error rates
  * Cache hit ratio
* Linked CloudFront metrics to **CloudWatch** for deeper insights.

**Screenshots:**

![Metrics Dashboard](./Metrics.png)
![Setup Screenshot](./Screenshot.png)

---

## 🧠 Lessons Learned

* CloudFront’s **Logging tab** is now separate in the new AWS console.
* Choose **Amazon S3 (not S3 Legacy)** when creating access log destinations.
* Real-time logs are optional and cost extra; standard logs are perfect for free-tier setups.
* S3 versioning adds rollback safety and enhances operational reliability.

---

## ✅ Phase 3 Summary

| Component          | Status    | Notes                              |
| ------------------ | --------- | ---------------------------------- |
| CloudFront Logging | ✅ Enabled | Logs to `my-first-aws-site-logs`   |
| S3 Versioning      | ✅ Enabled | Both main & logs buckets           |
| Metrics Monitoring | ✅ Active  | CloudFront & CloudWatch integrated |

---

## 🧾 Repository Structure

```
├── index.html
├── styles.css
├── scripts.js
├── Screen.png
├── Metrics.png
├── Screenshot.png
├── .github/
│   └── workflows/
│       └── deploy.yml
├── README.md
```

---

## 🚀 What’s Next — Phase 4

The next step focuses on **security and automation**:

* Implementing **IAM hardening**
* Setting up **CloudFront OAI/OAC** for secure bucket access
* Adding **AWS WAF** for protection from common attacks
* Optionally integrating automated security scans in the pipeline

---

## 💡 Skills Demonstrated

* AWS S3 Website Hosting
* CloudFront Distribution & Caching
* CI/CD via GitHub Actions
* Access Logging & Monitoring
* Infrastructure Hardening
* Cost Optimization (Free Tier Compliance)

---

## 📜 License

This project is part of the **AWS Cloud Learning Series** — educational and open for reuse under MIT License.
