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
                // Usamos la IP especial de Docker Desktop para comunicarse con tu Windows
                withEnv(['DOCKER_HOST=tcp://host.docker.internal:2375']) {
                    sh 'docker compose down'
                }
            }
        }

        stage('docker compose up -d') {
            steps {
                withEnv(['DOCKER_HOST=tcp://host.docker.internal:2375']) {
                    sh 'docker compose up -d'
                }
            }
        }

        stage('docker ps verificación') {
            steps {
                withEnv(['DOCKER_HOST=tcp://host.docker.internal:2375']) {
                    sh 'docker ps'
                }
            }
        }
    }
}