pipeline {
    agent any

    tools {
        maven 'Maven-3.9'
    }

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/shubhamkalsait/EasyCRUD.git'
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
                sh 'mvn test'
            }
        }
    }

    post {
        success {
            echo 'Build Successfull'
        }
        failure {
            echo 'Build Failed!'
        }
    }
}
