pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }

        stage('Docker Info') {
            steps {
                echo 'Docker sera exécuté localement pour générer l image du projet.'
            }
        }
    }

    post {
        success {
            echo 'Pipeline exécuté avec succès.'
        }

        failure {
            echo 'Erreur dans le pipeline.'
        }
    }
}