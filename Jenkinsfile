pipeline {
    agent any 
    stages {
        stage('First Stage Name') {
            steps{
                echo "One" 
            }
        }
        stage('Second Stage Name') {
            steps{
               sh echo "Two"
               sh echo "echo ENV_URL is ${ENV_URL}"
            }
        }
        stage('Third Stage Name') {
            steps{
                sh '''echo AWS
                      echo DevOps
                      echo Bash
                   '''
            }
        }
    }
}