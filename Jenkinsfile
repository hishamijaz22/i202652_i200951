pipeline {
    agent any

    environment {
        DOCKER_USERNAME = credentials('docker-hub-credentials').username
        DOCKER_PASSWORD = credentials('docker-hub-credentials').password
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/hishamijaz22/i202652_i200951.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t my-app .'
            }
        }

        stage('Push Docker Image') {
            steps {
                script {
                    bat "docker login -u ${DOCKER_USERNAME} -p ${DOCKER_PASSWORD}"
                    bat 'docker push my-app'
                }
            }
        }
    }
}
