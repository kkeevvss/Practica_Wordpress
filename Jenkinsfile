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
                withEnv(['DOCKER_HOST=unix:///var/run/docker.sock']) {
                    sh 'docker compose down'
                }
            }
        }

        stage('docker compose up -d') {
            steps {
                withEnv(['DOCKER_HOST=unix:///var/run/docker.sock']) {
                    sh 'docker compose up -d'
                }
            }
        }

        stage('docker ps verificación') {
            steps {
                withEnv(['DOCKER_HOST=unix:///var/run/docker.sock']) {
                    sh 'docker ps'
                }
            }
        }
    }
}