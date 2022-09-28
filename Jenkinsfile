pipeline {
    agent any
    
    stages{
        stage('clean')
        {
            steps{
                sh 'mvn clean'
             }
        }
        
        stage('compile')
        {
            steps{
                sh 'mvn compile'
            }
          stage('dockerize')
        {
            steps{
                sh 'docker build -t user-service:latest .'
            }
        }
       /*  stage('quality')
        {
            steps{
               
                sh 'mvn sonar:sonar'
            }
        }*/
        
        
        stage('test')
        {
            steps{
                echo 'running tests...'
                sh 'mvn test'
            }
        }
        
        stage('jar')
        {
            steps{
                sh 'mvn package -DskipTests=true'
            }
        }
   }
}