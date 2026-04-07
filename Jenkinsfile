pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/ahmedalaa-devops/docker-nodejs-jenkins.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t nodejs-app:v1 .'
            }
        }

        stage('Run App') {
            steps {
                sh 'docker run -d -p 3000:3000 nodejs-app:v1'
            }
        }

        stage('Verify') {
            steps {
                sh 'docker ps'
            }
        }
    }
}
