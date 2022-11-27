pipeline {
    agent any 
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    triggers { pollSCM('H/2 * * * *')}
    environment {
        ENV_URL = "pipeline.google.com"
        ACCESS_KEY = credentials('AWS_ACCESS_KEY')
        SSH_CRED = credentials('SSH-CRED')
    }
    options {
        buildDiscarder(logRotator(numToKeepStr: '3'))
        disableConcurrentBuilds()
        timeout(time: 1, unit: 'MINUTES') 
    }
    stages {
        stage('First Stage Name') {
            steps{
                sh "mvn --version"
                sh "echo One" 
                sh "env"
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