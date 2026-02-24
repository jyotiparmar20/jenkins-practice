

pipeline {
    agent any

    tools {
        maven 'Maven-3'
    }

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/jyotiparmar20/jenkins-practice.git'
            }
        }

        stage('Run') {
            steps {
                echo 'Running application setup...'
                sh 'ls -la'
            }
        }

        stage('Build') {
            steps {
                dir('EasyCRUD/backend') {
                    sh 'mvn clean package -DskipTests'
                }
            }
        }

        stage('Test') {
            steps {
                dir('EasyCRUD/backend') {
                    sh 'mvn test'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                echo 'Deployment successful!'
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
