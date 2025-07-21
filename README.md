# Corizo_Minor_Project
This project demonstrates how to host a **static website** using **Amazon S3**. The hosted site features a **College Admission Form** built using HTML, CSS, and JavaScript. This project was developed as part of my mentor-led virtual internship in **Cloud Computing** from **Corizo**.

---

## 📌 Project Overview

- ✅ Frontend: HTML, CSS, JavaScript
- ✅ Cloud Platform: Amazon Web Services (AWS)
- ✅ Services Used: S3, IAM, AWS CLI
- ✅ Hosting Type: Static Website Hosting on S3

---

## 🎯 Objective

To gain hands-on experience with AWS by:
- Designing a simple college admission form
- Hosting it on S3 as a static website
- Managing bucket permissions and public access
- Troubleshooting access errors like 403 Forbidden

---

## 🚀 Live Website

👉 [Click here to visit the hosted form](http://static-admission-form.s3-website.ap-south-1.amazonaws.com)

> _Note: Replace `mybucky123` with your actual bucket name if different._

---

## 🔧 Setup Instructions

### 1. Create an S3 Bucket
- Go to AWS Console > S3
- Create a new bucket (must be globally unique)

### 2. Enable Static Website Hosting
- Properties > Static Website Hosting > Enable
- Index document: `index.html`

### 3. Upload Files
```bash
aws s3 cp . s3://your-bucket-name/ --recursive
4. Set Bucket Policy
json
Copy
Edit
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}
5. Disable Public Access Block
Go to Permissions > Block Public Access

Uncheck all options

⚠️ Common Issue
If you see a 403 Forbidden error:

Make sure files (especially index.html) are directly in the root of the bucket, not inside a sub-folder.

Ensure the bucket policy and block public access settings are properly configured.

📚 What I Learned
AWS S3 static website hosting

Using AWS CLI for uploads

Bucket policy configuration

Troubleshooting permission/access errors

👨‍💻 Author
Shubham Hajela
B.Tech CSE Student | Cloud Computing Intern at Corizo
