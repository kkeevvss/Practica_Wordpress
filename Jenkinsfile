pipeline {
    agent any

    stages {
        stage('Checkout desde Git') {
            steps {
                checkout scm
            }
        }

        stage('docker compose down') {
            steps {
                sh 'docker compose down'
            }
        }

        stage('docker compose up -d') {
            steps {
                sh 'docker compose up -d'
            }
        }

        stage('docker ps verificacion') {
            steps {
                sh 'docker ps'
            }
        }
    }
}