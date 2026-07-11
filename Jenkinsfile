pipeline {
    agent any

    stages {
        stage('Checkout desde Git') {
            steps {
                git branch: 'main', url: 'https://github.com/kkeevvss/Practica_Wordpress.git'
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

        stage('docker ps verificación') {
            steps {
                sh 'docker ps'
            }
        }
    }
}