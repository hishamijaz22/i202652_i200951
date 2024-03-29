pipeline {
    agent any

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
                withCredentials([usernamePassword(credentialsId: 'docker-hub-credentials', usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) {
                    bat 'docker login -u %hishamijaz22% -p %hisham123%'
                    bat 'docker push my-app'
                }
            }
        }
    }
}
