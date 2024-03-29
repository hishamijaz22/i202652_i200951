pipeline {
    agent any

    environment {
        DOCKER_USERNAME = 'hishamijaz22'
        DOCKER_PASSWORD = 'hisham123'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the repository
                git 'https://github.com/hishamijaz22/i202652_i200951.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                // Build the Docker image
                sh 'docker build -t my-app .'
            }
        }

        stage('Push Docker Image') {
            steps {
                // Log in to Docker Hub
                withCredentials([usernamePassword(credentialsId: 'docker-hub-credentials', usernameVariable: 'hishamijaz22', passwordVariable: 'hisham123')]) {
                    sh 'docker login -u $hishamijaz22 -p $hisham123'
                }

                // Push the Docker image to Docker Hub
                sh 'my-app'
            }
        }
    }
}
