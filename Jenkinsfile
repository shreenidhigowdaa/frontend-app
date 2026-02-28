pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t frontend-app .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker stop frontend-container || true'
                sh 'docker rm frontend-container || true'
                sh 'docker run -d -p 80:80 --name frontend-container frontend-app'
            }
        }
    }
}
