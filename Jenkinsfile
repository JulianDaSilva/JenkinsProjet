pipeline {
    agent any
    tools { 
        maven 'Maven1' 
        jdk 'java11' 
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                bat 'mvn compile'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                bat 'mvn test'
            }
        }
        stage('Install') {
            steps {
                echo 'Deploying....'
                bat 'mvn clean install'
            }
        }            
    }
}
