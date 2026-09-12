

pipeline {
agent any

```
stages {

    stage('Checkout') {
        steps {
            checkout scm
        }
    }

    stage('Build Docker Image v2') {
        steps {
            sh 'docker build -t globalbridge-web:v2 .'
        }
    }

    stage('Verify Docker Image v2') {
        steps {
            sh 'docker images globalbridge-web:v2'
        }
    }

    stage('Deployment Release') {
        steps {
            echo 'GlobalBridge Version 2.0 Docker image built successfully'
            echo 'Ready for Kubernetes deployment'
        }
    }
}

post {
    success {
        echo 'GlobalBridge v2 CI pipeline completed successfully'
    }

    failure {
        echo 'GlobalBridge v2 CI pipeline failed'
    }
}
```

}

