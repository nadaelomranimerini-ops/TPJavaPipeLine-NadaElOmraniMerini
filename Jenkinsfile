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

        stage('Docker Build') {
            steps {
                sh 'docker build -t java-pipeline-app .'
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