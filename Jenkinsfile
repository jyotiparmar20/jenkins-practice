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
            stage('Quality Gate') {
                  steps {
                     timeout(time: 5, unit: 'MINUTES') {
                     waitForQualityGate abortPipeline: true
             } 
         }
     } 
        
         stage('Upload Artifact to S3') {
             steps {
                 sh '''
               aws s3 cp backend/target/*.jar \
               s3://jo-bkt-1/
                  '''
          }
     }          
   }     
}          
        

    

