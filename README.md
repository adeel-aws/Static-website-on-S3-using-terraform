# 🌐 Terraform Static Website on S3

This project demonstrates **infrastructure as code** with Terraform to create an **AWS S3 bucket** configured for **static website hosting**. The project also automatically uploads your static website files to the bucket and provides the **website endpoint** as output.

---

## 🏗️ Project Overview

- **Static Website:** HTML/CSS files hosted on S3  
- **Infrastructure as Code:** Terraform provisions S3 bucket with optional features  
- **Automated Upload:** Website files (e.g., `index.html`, `img/`) uploaded automatically  
- **Output:** S3 website endpoint provided for immediate access  
- **Secure Defaults:** Private bucket by default with optional public access  

---

## 🗂️ Folder Structure

```text
project-root/
├── App/
│   ├── index.html            # Main HTML page
│   └── img/                  # Image assets
├── Terraform/
│   ├── main.tf               # Terraform resources (S3 bucket, objects)
│   ├── variables.tf          # Terraform input variables
│   ├── outputs.tf            # Terraform outputs (website endpoint)
│   └── terraform.tfvars      # Variable values
```

---

## ⚡ How It Works

1. **Terraform S3 Bucket:**  
   - Creates an S3 bucket with optional **public access**, **versioning**, **lifecycle rules**, and **logging**.  
   - Enables **static website hosting**.  

2. **Upload Static Website:**  
   - Terraform resource `aws_s3_object` uploads website files (`index.html`, `img/` folder) to the bucket.  
   - Bucket policy ensures objects are accessible if public access is enabled.  

3. **Website Endpoint Output:**  
   - Terraform outputs the S3 static website URL.  
   - Open the URL in a browser to view your live site.  

---

## 📦 Key Features

- Fully automated S3 static website deployment  
- Optional **public access**, **versioning**, **logging**, **lifecycle rules**  
- Automatic upload of website content via Terraform  
- Immediate output of website endpoint  
- Modular and reusable Terraform module  

---

## 🛠️ Deployment Instructions

1. **Configure Terraform Variables:**  
   Update `terraform.tfvars` with your desired bucket name, public access, logging, and lifecycle options.

2. **Initialize Terraform:**  
   ```bash
   cd Terraform
   terraform init
   ```

3. **Apply Terraform:**  
   ```bash
   terraform apply -auto-approve
   ```

4. **Access Website:**  
   - Check the Terraform output for `website_endpoint`  
   - Open the URL in a browser to view the live website  

---

## ✅ Outcome

- S3 bucket created and configured for static hosting  
- Website files automatically uploaded  
- Live site accessible immediately through S3 website endpoint  
- Infrastructure fully versioned and reproducible with Terraform  

---

## ⚙️ Future Enhancements

- Add **custom domain** and **SSL via CloudFront**  
- Automate deployment with **CI/CD pipeline**  
- Support multiple environments (dev, staging, prod)  
- Add monitoring for bucket usage and file changes  
