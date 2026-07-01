pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                echo 'Repository cloned successfully'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t hello-world:v1 .'
            }
        }

        stage('Docker Images') {
            steps {
                bat 'docker images'
            }
        }
    }
}