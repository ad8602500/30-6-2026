pipeline {
    agent any

    environment {
        IMAGE_NAME = "ad8602500/hello-world:v1"
    }

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t %IMAGE_NAME% .'
            }
        }

        stage('Login to Docker Hub') {
            steps {
                echo 'Repository cloned successfully'
            }
        }

        stage('Push Docker Image') {
            steps {
                bat 'docker push %IMAGE_NAME%'
            }
        }

        stage('Logout') {
            steps {
                bat 'docker logout'
            }
        }
    }
}