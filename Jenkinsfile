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
                sh 'mvn clean verify'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'mvn test'
            }
        }
        stage('Install') {
            steps {
                echo 'Deploying....'
                sh 'mvn clean install'
            }
        }            
    }
}
