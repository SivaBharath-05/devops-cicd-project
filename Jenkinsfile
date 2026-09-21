pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/SivaBharath-05/devops-cicd-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-cicd-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker stop devops-app || true'
                sh 'docker rm devops-app || true'
                sh 'docker run -d -p 80:80 --name devops-app devops-cicd-app'
            }
        }
    }
}
