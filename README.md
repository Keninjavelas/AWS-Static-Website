# ☁️ AWS Static Website Hosting Project

### 🚀 Project Overview

This project demonstrates how to host and distribute a **static website** using **Amazon S3** and **Amazon CloudFront** — two of the most commonly used AWS services for scalable and cost-efficient web hosting.

It’s the first step in my cloud learning journey, showing hands-on experience with **core AWS infrastructure** concepts like storage, access control, and global content delivery.

---

### 🧱 Architecture Overview

**Services Used:**

* **Amazon S3** – Stores and serves static files (`index.html`, CSS, images, etc.)
* **Amazon CloudFront** – Content Delivery Network (CDN) to cache and deliver content globally
* **AWS IAM** – Manages access permissions to the S3 bucket
* **AWS Route 53** *(optional)* – Can be used later for a custom domain
* **AWS Certificate Manager (ACM)** *(optional)* – Enables HTTPS for custom domains

**Architecture Diagram:**

```
[User Browser]
      │
      ▼
[Amazon CloudFront Distribution]
      │
      ▼
[Amazon S3 Bucket (Static Website Hosting)]
```

---

### 🧰 Tech Stack

* **HTML5**, **CSS3**, **JavaScript**
* **Amazon S3** (Static Hosting)
* **Amazon CloudFront** (Global CDN)
* **AWS Management Console**

---

### ⚙️ Steps to Deploy

1. **Create S3 Bucket**

   * Bucket name: `my-first-aws-site-aryan`
   * Disable “Block all public access”
   * Upload website files (`index.html`, `style.css`, etc.)
   * Enable **Static website hosting**
     → Choose “Use this bucket to host a website”
     → Index document: `index.html`

2. **Set Bucket Policy**

   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "PublicReadGetObject",
         "Effect": "Allow",
         "Principal": "*",
         "Action": "s3:GetObject",
         "Resource": "arn:aws:s3:::my-first-aws-site-aryan/*"
       }
     ]
   }
   ```

3. **Test Website (S3 URL)**

   * Example: `http://my-first-aws-site-aryan.s3-website-us-east-1.amazonaws.com/`

4. **Create CloudFront Distribution**

   * Origin domain: select your **S3 website endpoint**
   * Viewer protocol policy: **Redirect HTTP to HTTPS**
   * Default root object: `index.html`
   * Wait for deployment (~10–15 minutes)

5. **Access via CloudFront URL**

   * Example: `https://d78vjzv8z61e6.cloudfront.net/`

---

### 🌎 Outcome

✅ Fully hosted website on AWS
✅ Globally distributed via CloudFront CDN
✅ HTTPS-enabled, highly scalable, and cost-efficient
✅ Demonstrates knowledge of core AWS concepts (S3, CloudFront, IAM)

---

### 📈 Future Enhancements

* Add **custom domain** via Route 53 + ACM certificate
* Automate deployment using **GitHub Actions** or **CodePipeline**
* Integrate **CloudWatch** for access logs and monitoring

---

### 🧑‍💻 Author

**Aryan Kapoor**
AWS Cloud Learner | Aspiring Cloud/DevOps Engineer
📚 Currently pursuing AWS Cloud Practitioner Certification

---
