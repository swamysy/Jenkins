pipeline {
    agent any 
    environment {
        ENV_URL = "pipeline.google.com"
        ACCESS_KEY = credentials('AWS_ACCESS_KEY')
    }
    options {
        buildDiscarder(logRotator(numToKeepStr: '3'))
        disableConcurrentBuilds()
    }
    stages {
        stage('First Stage Name') {
            steps{
                sh "echo One" 
                sh "env"
                sh "sleep 1000"
            }
        }
        stage('Second Stage Name') {
            steps{
               sh "echo Two"
               sh "echo ENV_URL is ${ENV_URL}"
               sh "echo $ACCESS_KEY"
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