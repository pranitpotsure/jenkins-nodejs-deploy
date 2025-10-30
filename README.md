# 🚀 Jenkins Freestyle Pipeline – Node.js App Deployment

## 📘 Overview
This project demonstrates a **Jenkins Freestyle Pipeline** setup that automatically deploys a Node.js application.  
Each stage (job) in Jenkins performs a specific part of the deployment pipeline — from environment setup to final deployment.

---

## 🧩 Pipeline Jobs
| Stage | Job Name | Description |
|--------|-----------|-------------|
| 1️⃣ | 01-env-setup | Sets up Node.js and required environment on the target server |
| 2️⃣ | 02-pull-repo | Clones the latest source code from GitHub |
| 3️⃣ | 03-install-deps | Installs dependencies using `npm install` |
| 4️⃣ | 04-deploy-app | Starts or restarts the Node.js application (using PM2 or `node app.js`) |

---

## ⚙️ Tools & Technologies
- **Jenkins** (Freestyle jobs)
- **Node.js** & **npm**
- **GitHub** (for source code)
- **Linux (Ubuntu)** for deployment environment
- **PM2** (optional) for Node.js process management

---

## 📸 Screenshots
| Step | Description | Screenshot |
|------|--------------|-------------|
| ✅ | Jenkins Job List | ![Job List](./screenshots/job-list.png) |
| 🧩 | Console Output | ![Console Output](./screenshots/console-output.png) |
| 🌐 | Node.js App Deployed | ![App Deployed](./screenshots/deployed-app.png) |

---

## 🪜 How It Works
1. **Job 01-env-setup** installs Node.js:
   ```bash
   sudo apt update
   sudo apt install -y nodejs npm
   node -v
   npm -v
