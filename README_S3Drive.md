# 🚀 S3Drive – SaaS Employee Document Management System

![AWS](https://img.shields.io/badge/AWS%20S3-%23FF9900.svg?&style=for-the-badge&logo=amazon-aws&logoColor=white)
![CloudFront](https://img.shields.io/badge/CloudFront-%23FF9900.svg?&style=for-the-badge&logo=amazonaws&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node-dot-js&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)

---

**S3Drive** is a **SaaS-based secure employee document management system** that allows users to **create folders, upload files, and organize them** in a nested structure.  
Admins can configure whether storage is **Local** or **AWS S3**, and files are served via **AWS CloudFront** for optimized performance.

---

## 📸 Project Screenshots

### 🏠 Dashboard View
![Dashboard Screenshot](./assets/dashboard.png)

### 📂 File Explorer
![File Explorer Screenshot](./assets/upload-folder.png)

### ⚙️ Admin Settings
![Admin Settings Screenshot](./assets/admin-settings.png)

### ☁️ AWS S3 Bucket
![AWS S3 Console Screenshot](./assets/aws-console.png)

---

## 🧠 Project Overview

| Feature | Description |
|----------|--------------|
| 🌩️ **AWS S3 Integration** | Upload and manage files directly in an AWS S3 bucket |
| ⚡ **CloudFront CDN** | Serve S3 files via CloudFront for faster global delivery |
| 🧰 **Local or Cloud Storage** | Admin can switch between local server or AWS S3 |
| 👥 **Multi-user System** | Each employee has their own folders and files |
| 🔒 **Role-based Permissions** | Admin can control file read/write/delete access |
| 🗂️ **Nested Folder Management** | Create subfolders and organize documents |
| 📂 **Tree View File Explorer** | Clean UI to view folders/files hierarchically |
| 🧾 **Activity Logs** | Tracks uploads, downloads, and changes |
| ⚙️ **Admin Settings Panel** | Toggle storage, manage permissions, and monitor files |

---

## 🏗️ System Architecture

```mermaid
flowchart TD
    A[Employee/Client] -->|Upload File| B[Backend API - Express/Laravel]
    B -->|Check Storage Type| C{Local or AWS S3?}
    C -->|Local| D[Local Disk Storage]
    C -->|S3| E[AWS S3 Bucket]
    E --> F[CloudFront CDN]
    F -->|Serve Optimized File| A
    B --> G[Database (MySQL/PostgreSQL)]
    B --> H[Admin Settings & Permissions]
```

---

## ⚙️ Tech Stack

### Backend
- Node.js (Express) / Laravel (PHP)
- JWT Authentication
- AWS SDK (for S3 + CloudFront)

### Frontend
- React.js / Next.js 14
- TailwindCSS
- Axios

### Database
- MySQL / PostgreSQL

### Cloud
- AWS S3 (File Storage)
- AWS CloudFront (CDN)

---

## 🧩 API Endpoints

| Method | Endpoint | Description |
|---------|-----------|-------------|
| `POST` | `/api/login` | Authenticate user |
| `POST` | `/api/folders` | Create new folder |
| `GET` | `/api/folders/:id` | Get files/folders under folder |
| `POST` | `/api/files/upload` | Upload file to local/S3 |
| `GET` | `/api/files/:id` | Download file |
| `PATCH` | `/api/settings/storage` | Update storage mode |
| `GET` | `/api/admin/files` | List all files (Admin) |

---

## 🧰 Setup Instructions

### 1️⃣ Clone Repository
```bash
git clone https://github.com/yourusername/s3drive.git
cd s3drive
```

### 2️⃣ Install Dependencies
```bash
npm install
```

### 3️⃣ Configure Environment
Create `.env`:
```env
PORT=4000
DB_HOST=localhost
DB_USER=root
DB_PASS=
DB_NAME=s3drive

AWS_ACCESS_KEY_ID=your_access_key
AWS_SECRET_ACCESS_KEY=your_secret_key
AWS_REGION=ap-south-1
AWS_S3_BUCKET=your_bucket_name
AWS_CLOUDFRONT_URL=https://your-cloudfront-domain.cloudfront.net

STORAGE_TYPE=local
```

### 4️⃣ Run Application
```bash
npm run dev
```

### 5️⃣ Access App
- Frontend: http://localhost:3000
- Backend: http://localhost:4000/api

---

## ☁️ AWS Setup

1. Create **S3 Bucket**
2. Create **CloudFront Distribution**
3. Add credentials in `.env`

---

## 💡 Learning Outcomes

- AWS S3 SDK integration
- CloudFront CDN configuration
- SaaS architecture & multi-user design
- Local + cloud file storage switching
- Secure file permissions

---

## 🧑‍💻 Author

**Faaiz Uddin**  
Full Stack Developer | AWS | SaaS | Node.js | React.js  
📧 hello@edusuite.pk

---

## ⭐ Support

If you like this project, please ⭐ the repo and share it!
