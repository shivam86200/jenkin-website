pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/YOUR_USERNAME/JenkinsProject.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t mywebsite .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker stop mywebsite || true
                docker rm mywebsite || true
                docker run -d --name mywebsite -p 8081:80 mywebsite
                '''
            }
        }
    }
}