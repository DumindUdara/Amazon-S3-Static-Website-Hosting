# Amazon-S3-Static-Website-Hosting
# Host Your CV as a Static Webpage on AWS S3 🚀

Ever thought about making your resume stand out by hosting it as a webpage? 🌐 This guide will walk you through the process of turning your CV into a sleek online webpage using Amazon's S3 static website hosting.

---

## **Step-by-Step Instructions**

### **Step 1: Prerequisites**
1. An **AWS account**.
2. Your CV formatted as an `index.html` file.
3. Basic knowledge of HTML and AWS S3.

---

### **Step 2: Create an S3 Bucket**
1. **Login to AWS Management Console** and navigate to the [S3 service](https://aws.amazon.com/s3/).
2. Click **"Create bucket"**.
3. Enter a unique **bucket name** (e.g., `dumindu-cv`).
4. Choose a region closest to you.
5. Uncheck **"Block all public access"** for website hosting purposes.
6. Acknowledge the warning and click **"Create bucket"**.

---

### **Step 3: Upload Your CV**
1. Open the newly created bucket.
2. Click **"Upload"** and add your `index.html` file.
3. Click **"Upload"** to complete.

---

### **Step 4: Configure Static Website Hosting**
1. Go to the **"Properties"** tab of your bucket.
2. Scroll down to **"Static website hosting"** and click **"Edit"**.
3. Select **"Enable"**.
4. Enter `index.html` as the **Index document**.
5. Save changes.

---

### **Step 5: Set Bucket Permissions**
1. Go to the **"Permissions"** tab of your bucket.
2. Under **Bucket Policy**, click **"Edit"**.
3. Add the following JSON policy, replacing `your-bucket-name` with your bucket name:
   ```json
   {
       "Version": "2012-10-17",
       "Statement": [
           {
               "Effect": "Allow",
               "Principal": "*",
               "Action": "s3:GetObject",
               "Resource": "arn:aws:s3:::your-bucket-name/*"
           }
       ]
   }

