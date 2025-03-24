pipeline {
    agent any
    environment {
        DOCKER_IMAGE = ""
    }
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/poush4/Django-app.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE .'
            }
        }
        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 8000:8000 $DOCKER_IMAGE'
            }
        }
    }
}
