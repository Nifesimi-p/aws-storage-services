# aws-storage-services
# AWS S3 Static Website Hosting with AWS CLI

This project demonstrates how to use **AWS S3** and the **AWS CLI** to create and manage S3 buckets, upload files, configure static website hosting, and set public permissions.

---

## 📁 Repository Name
**aws-storage-services**

---

## 👤 Mentee Contribution
The HTML files used for the static website were provided by **Frontend Mentee: Nifesimi**.

---

## 📌 Objectives

1. Create an S3 bucket
2. Upload, retrieve, and delete objects
3. Configure public access permissions
4. Host a static website using S3
5. Manage all operations using the AWS CLI
6. Document the process with commands, outputs, and screenshots

---

## 🧰 Tools Used

- AWS CLI
- Git & GitHub
- Amazon S3 (Simple Storage Service)
- HTML (static files)

---

## ✅ Step-by-Step Process

### 1. Create an S3 Bucket

```bash
aws s3api create-bucket --bucket preciousnife --region us-east-1
