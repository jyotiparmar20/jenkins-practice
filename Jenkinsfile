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

         stage ('sonarQube Analysis') {
            steps{
                withsonarQubeEnv ('sonarqube-server') {
                    sh '''
                    mvn sonar:sonar \
                    -Dsonar.projectKey=EasyCRUD \
                    -Dsonar .projectName=EasyCRUD
                    '''
        }
     } 
   }
}

        
