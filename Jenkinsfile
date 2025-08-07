pipeline {
  agent any

  environment {
    SONARQUBE_SERVER = 'SonarQube'
    SONAR_TOKEN = credentials('SONAR_TOKEN')  // You must create this in Jenkins Credentials
  }

  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/marioaaziz/CI-CD-Project.git'
      }
    }

    stage('SonarQube Analysis') {
      steps {
        withSonarQubeEnv(SONARQUBE_SERVER) {
          sh """
            sonar-scanner \
              -Dsonar.projectKey=devops-app \
              -Dsonar.sources=. \
              -Dsonar.token=$SONAR_TOKEN
          """
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
