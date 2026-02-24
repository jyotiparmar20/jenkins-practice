pipeline {
    agent any

    stages {

        stage('Run') {
            steps {
                echo 'Running application setup...'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                sh '''
                cd backend
                mvn clean package'''
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                echo 'Deployment successful!'
            }
        }
    }
}
