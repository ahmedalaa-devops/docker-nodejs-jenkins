pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/LukeMwila/docker-nodejs-application.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t nodejs-app:v1 .'
            }
        }

        stage('Run App') {
            steps {
                sh 'docker rm -f nodejs-app || true'
                sh 'docker run -d --name nodejs-app -p 8082:3000 nodejs-app:v1'
            }
        }

        stage('Verify') {
            steps {
                sh 'docker ps'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
        failure {
            echo 'Pipeline failed. Check logs.'
        }
        success {
            echo 'Pipeline succeeded!'
        }
    }
}
