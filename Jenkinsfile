pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out GlobalBridge source code from GitHub'
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Building GlobalBridge Docker image v2'
                sh 'docker build -t globalbridge-web:v2 .'
            }
        }

        stage('Verify Docker Image') {
            steps {
                echo 'Verifying GlobalBridge Docker image v2'
                sh 'docker images globalbridge-web:v2'
            }
        }

        stage('Release Verification') {
            steps {
                echo 'GlobalBridge Dashboard Version 2.0 build completed'
                echo 'Docker image: globalbridge-web:v2'
                echo 'Ready for Kubernetes deployment'
            }
        }
    }

    post {
        success {
            echo 'SUCCESS: GlobalBridge v2 CI pipeline completed successfully'
        }

        failure {
            echo 'FAILURE: GlobalBridge v2 CI pipeline failed'
        }
    }
}
