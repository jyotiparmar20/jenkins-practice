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
                 dir('backend') {
                sh ' mvn clean package'
            }
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
