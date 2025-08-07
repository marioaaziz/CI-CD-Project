pipeline {
  agent any

  environment {
    SONARQUBE_SERVER = 'SonarQube'
  }

  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/YOUR_USERNAME/CICD-Project.git'
      }
    }

    stage('SonarQube Analysis') {
      steps {
        withSonarQubeEnv(SONARQUBE_SERVER) {
          sh 'sonar-scanner -Dsonar.projectKey=devops-app -Dsonar.sources=.'
        }
      }
    }

    stage('Build Backend Docker Image') {
      steps {
        sh 'docker build -t devops-backend ./backend'
      }
    }

    stage('Build Frontend Docker Image') {
      steps {
        sh 'docker build -t devops-frontend ./frontend'
      }
    }

    stage('Deploy to Kubernetes') {
      steps {
        sh 'kubectl apply -f k8s/'
      }
    }
  }
}