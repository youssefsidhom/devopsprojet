pipeline {
    agent any
    environment {
        docker_cred = credentials('docker_cred')
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build Backend') {
            steps {
                dir('backend'){
                sh 'mvn clean package'
            }
        }
        }
            stage('Unit Tests') {
            steps {
                dir('backend'){
                        sh 'mvn test'
                }
            }
        }
        stage('Generate Code Coverage Report') {
        steps {
        dir('backend'){
        sh 'mvn jacoco:report'
    }
    }
}
        stage('SonarQube Analysis') {
            steps {
                dir('backend') {
                       withSonarQubeEnv('sonarserver') {
                                      sh 'mvn sonar:sonar -Dsonar.java.binaries=target/classes'
            }
                }
               
        }
        }

        stage('Deploy to Nexus') {
    steps {
        dir('backend'){
            sh 'mvn deploy -DskipTests'
                }        
    }
}
