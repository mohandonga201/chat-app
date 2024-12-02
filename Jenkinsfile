pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', credentialsId: 'jenkins-git', url: 'https://github.com/mohandonga201/chat-app.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t chat-app .'
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    sh 'docker run -d -p 3000:3000 chat-app'
                }
            }
        }
    }
}
