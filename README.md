# 🛠️ CI/CD Pipeline with Jenkins, SonarQube & Docker

This project demonstrates a simple CI/CD pipeline that:
- Pulls code from GitHub
- Analyzes it with SonarQube
- Builds a Docker image
- Deploys it to a live server

---

## 🚀 Tech Stack
- **GitHub** – version control
- **Jenkins** – CI/CD automation
- **SonarQube** – static code analysis
- **Docker** – containerization & deployment

---

## 📁 Project Structure
.
├── backend/
├── frontend/
│ ├── public/
│ │ └── index.html
│ └── src/
├── Dockerfile
├── Jenkinsfile
├── docker-compose.yml
└── sonar-project.properties


---

## ⚙️ Jenkins Pipeline Steps

1. Clone code from GitHub
2. Run SonarQube analysis
3. Build Docker image
4. Deploy container to server on port 8085

---

## 🌐 Deployment

The app is accessible at:  

(http://35.95.143.143:8085/)
(Currently shows a static frontend via NGINX)

---

## 📸 Screenshots

> Add your screenshots here using:
> `![desc](img/screenshot.png)`

---

## 👨‍💻 Author

Mario Aziz  
DevOps | Cloud Engineer
