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
                echo " build step...."
            }
        }

        stage('Run App') {
            steps {
                sh ' docker run -d -p 80:80 nginx '
            }
        }

        stage('Verify') {
            steps {
                sh 'docker ps'
            }
        }
    }
}
