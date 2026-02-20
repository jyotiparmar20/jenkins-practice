pipeline {
    agent any

    environment {
        APP_NAME = "test-app"
    }

    stages {

        stage('Checkout') {
            steps {
                echo "Cloning the repository..."
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Building ${test-app}"
                sh "echo Build completed"
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                sh "echo Tests successful"
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying ${test-app}"
                sh "echo Deployment done"
            }
        }
    }

    
}
