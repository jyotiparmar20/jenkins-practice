pipeline {
    agent any

    environment {
        APP_NAME = "Demo App"
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
                echo "Building ${APP_NAME}"
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
                echo "Deploying ${APP_NAME}"
                sh "echo Deployment done"
            }
        }
    }

    post {
        always {
            echo "Pipeline execution finished."
        }
        success {
            echo "Pipeline executed successfully!"
        }
        failure {
            echo "Pipeline failed!"
        }
    }
}
