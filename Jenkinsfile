pipeline {
    agent any
    tools { 
        maven 'Maven1' 
        jdk 'java11' 
    }
    environment {
        NEXUS_VERSION = "nexus3"
        NEXUS_PROTOCOL = "http"
        NEXUS_URL = "localhost:8081"
        NEXUS_REPOSITORY = "maven-nexus"
        NEXUS_CREDENTIAL_ID = "nexus-user-credentials"
    }
    stages {
        stage("Clone code from VCS") {
            steps {
                script {
                    git 'https://github.com/JulianDaSilva/JenkinsProjet';
                }
            }
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
