pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
     stage('Build Backend') {
            steps {
                // Change to the Spring Boot project directory
                dir('path/to/your/spring/boot/app') {
                    // Use Maven to build the application
                    sh 'mvn clean package'
                }
            }
        }
        /*
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        
               stage('Build Frontend') {
            steps {
                // Change to the Angular project directory
                dir('path/to/your/angular/app') {
                    // Install dependencies
                    sh 'npm install'

                    // Build the Angular application
                    sh 'ng build --prod'
                }
            }
        }
        */
    
    }
}

