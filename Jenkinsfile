pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/shubhamkalsait/EasyCRUD.git'
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

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('sonarqube-server') {
                    sh '''
                    cd backend
                    mvn sonar:sonar \
                    -Dsonar.projectKey=EasyCRUD \
                    -Dsonar.projectName=EasyCRUD
                    '''
                }
            }
        }

    }
}
