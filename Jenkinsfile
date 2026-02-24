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
                sh '''
                cd backend
                mvn clean package -DskipTests
                '''
            }
        }
    }           
}
