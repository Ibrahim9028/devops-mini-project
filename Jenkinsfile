


pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t globalbridge-web:v1 .'
            }
        }

        stage('Verify Docker Image') {
            steps {
                sh 'docker images globalbridge-web:v1'
            }
        }
    }

    post {
        success {
            echo 'GlobalBridge CI pipeline completed successfully'
        }
        failure {
            echo 'GlobalBridge CI pipeline failed'
        }
    }
}
