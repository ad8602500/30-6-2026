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
        withCredentials([usernamePassword(
            credentialsId: 'dockerhub-creds',
            usernameVariable: 'DOCKER_USER',
            passwordVariable: 'DOCKER_PASS'
        )]) {
            bat '''
            docker login -u "%DOCKER_USER%" -p "%DOCKER_PASS%"
            '''
        }
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