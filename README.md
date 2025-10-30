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
### 1. **Job 01-env-setup** installs Node.js:
```
  sudo apt update -y
  #Install Node.js 
  apt install nodejs -y
  #Install npm
 sudo apt install npm -y
  #Install PM2 globally for Jenkins user
 sudo npm install -g pm2 
 ```  

### 2. **Job 02-pull-repo** clones the project:

```git clone https://github.com/iamtruptimane/node-js-app-CICD```


### 3. **Job 03-install-deps** installs dependencies:
```
 cd "/var/lib/jenkins/workspace/02-pull-repo"
 npm install
```

### 4. **Job 04-deploy-app** starts the application:
```
 cd "/var/lib/jenkins/workspace/02-pull-repo"
 sudo pm2 start app.js --name node-app || sudo pm2 restart node-app
```

## 🎯 Outcome
Fully automated Node.js app deployment through Jenkins Freestyle Jobs.
Modular design — each job can be tested independently.
Great base for migrating to a Declarative Jenkinsfile pipeline in the future.

## 👨‍💻 Author
Pranit Potsure
💼 DevOps Enthusiast | Cloud Learner
🔗 LinkedIn Profile
