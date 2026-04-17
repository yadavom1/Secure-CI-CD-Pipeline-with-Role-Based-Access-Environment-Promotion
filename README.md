# Secure-CI-CD-Pipeline-with-Role-Based-Access-Environment-Promotion

This project demonstrates how to build a secure CI/CD pipeline using Jenkins, GitHub, and Amazon Web Services (EC2 &amp; IAM).

# 🌟 1. Architecture Overview  

Code Commit → Build → Unit Test → Dev → Staging → Approval → Production

# 🌍 Environment Setup

- Dev Environment (EC2 Instance)
- Staging Environment (EC2 Instance)
- Production Environment (EC2 Instance)

# 🗂 2. Project Structure  

```
├── app/
│   └── sample web application
├── Jenkinsfile
├── scripts/
│   └── deployment scripts
└── README.md
```

---

# ⚙️ Technologies Used

- Jenkins – CI/CD pipeline automation
- GitHub – Source code repository
- Amazon Web Services – Infrastructure
- Amazon EC2 – Hosting environments
- AWS IAM – Access control

---
# 🚀 Jenkins Pipeline Stages

```
1️⃣ Build
Compile application code
Prepare artifacts

2️⃣ Unit Testing
Run automated tests
Ensure code quality

3️⃣ Deploy to Dev
Auto deployment to Dev EC2
Used for initial testing

4️⃣ Deploy to Staging
Deployment to staging server
Pre-production validation

5️⃣ Manual Approval Gate 🔒
Admin approval required
Prevents unauthorized production deployment

6️⃣ Deploy to Production
Final deployment
Restricted to authorized users only

# 🔐 Role-Based Access Control (RBAC)

👨‍💻 Developer Role

  -Can trigger builds
  -Can deploy to Dev & Staging
  -❌ Cannot deploy to Production

👨‍💼 Admin Role

 -Full access
 -✅ Can approve production deployment

# 📜 Sample Jenkinsfile

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building application...'
            }
        }

        stage('Unit Test') {
            steps {
                echo 'Running tests...'
            }
        }

        stage('Deploy to Dev') {
            steps {
                echo 'Deploying to Dev environment...'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to Staging environment...'
            }
        }

        stage('Approval') {
            steps {
                input message: 'Approve deployment to Production?', ok: 'Approve'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying to Production...'
            }
        }
    }
}

# 🔒 Security Improvements

✅ Production access restricted
✅ Manual approval enforced
✅ Role-based permissions implemented
✅ Environment isolation achieved
✅ Reduced risk of accidental deployment

# 📈 Key Benefits

- Improved security 🔐
- Better release control 🚦
- Reduced deployment risks ⚠️
- Enterprise-level pipeline design 🏢

# 📸 Important screenshots

1️⃣"All Instance"
 <img width="1919" height="1079" alt="Image" src="https://github.com/user-attachments/assets/a15cbaf9-a789-4e2a-bf30-2ababe57e83f" />

2️⃣"Jenkinsfile"
2️<img width="1919" height="1079" alt="Image" src="https://github.com/user-attachments/assets/cddc6af7-fdf2-4ce6-aaa7-ec99ee872962" />

3️⃣"Working CI/CD pipeline"
<img width="1919" height="1079" alt="Image" src="https://github.com/user-attachments/assets/35881ea2-7a91-4880-adba-643a579794c3" />

<img width="1919" height="1079" alt="Image" src="https://github.com/user-attachments/assets/43cbcf06-e103-4d7d-9730-3e94305ae13d" />

<img width="1919" height="1079" alt="Image" src="https://github.com/user-attachments/assets/24c12eeb-6b48-46d5-a4d9-b2d792cc22ca" />






