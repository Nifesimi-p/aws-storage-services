# aws-storage-services

Absolutely! Here's a **comprehensive `README.md`** tailored to your AWS S3 static website hosting task, including CLI commands, results, and details about the mentee's uploaded frontend files.

---

```markdown
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
```

---

### 2. Upload Objects to the Bucket

```bash
aws s3 cp index.html s3://preciousnife/
aws s3 cp about.html s3://preciousnife/
```

---

### 3. Retrieve Objects

```bash
aws s3 cp s3://preciousnife/index.html .
```

---

### 4. Delete Objects (if needed)

```bash
aws s3 rm s3://preciousnife/about.html
```

---

### 5. Enable Static Website Hosting

```bash
aws s3 website s3://preciousnife/ --index-document index.html
```

---

### 6. Configure Public Access Settings

#### Disable Block Public Access:

```bash
aws s3api put-public-access-block \
  --bucket preciousnife \
  --public-access-block-configuration '{"BlockPublicAcls":false,"IgnorePublicAcls":false,"BlockPublicPolicy":false,"RestrictPublicBuckets":false}'
```

#### Attach a Public Bucket Policy:

**bucket-policy.json**
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::preciousnife/*"
    }
  ]
}
```

**Apply the policy:**
```bash
aws s3api put-bucket-policy --bucket preciousnife --policy file://bucket-policy.json
```

---

### 7. Access the Website

The static website is now publicly available at:

```bash
http://preciousnife.s3-website-us-east-1.amazonaws.com
```

---

## 🖼️ Screenshots & Logs

- ✅ S3 bucket creation log
- ✅ Public access configuration
- ✅ Static website preview
- ✅ AWS CLI outputs

(Screenshots are included in the `screenshots/` folder.)

---

## 🧾 Notes

- Ensure your AWS CLI is configured with the appropriate IAM user credentials.
- Always verify public access settings before applying policies.
- For security, only host non-sensitive static content publicly.

---

## 🔗 Useful Commands Summary

| Action | Command |
|--------|---------|
| Create bucket | `aws s3api create-bucket --bucket BUCKET-NAME --region REGION` |
| Upload file | `aws s3 cp FILE s3://BUCKET/` |
| Enable hosting | `aws s3 website s3://BUCKET/ --index-document index.html` |
| Public access block off | `aws s3api put-public-access-block ...` |
| Add bucket policy | `aws s3api put-bucket-policy --bucket BUCKET --policy file://bucket-policy.json` |
| Get website URL | `http://<bucket-name>.s3-website-<region>.amazonaws.com` |

---

## 💡 Author

Precious Nifesi

---

## 📬 Feedback & Contributions

Feel free to fork, clone, and submit a pull request. For questions or improvements, open an issue!

```

---

Let me know if you'd like me to help create the `screenshots/` folder or draft a `.gitignore` for good repo hygiene!
