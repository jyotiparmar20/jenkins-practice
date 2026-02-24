pipeline {
    agent any

    stages {
        stage('checkout') {
            steps {
                git branch: 'main' url: 'https://github.com/jyotiparmar20/jenkins-practice.git'
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
