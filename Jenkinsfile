pipeline {
    agent any
    stages {
           /*
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
       
     
     stage('Build Backend') {
            steps {
                // Change to the Spring Boot project directory
                dir('DevOps_Project-20231016T100739Z-001/DevOps_Project') {
                    // Use Maven to build the application
                    sh 'mvn clean package'
                }
            }
        }
        
       
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
       
        
               stage('Build Frontend') {
            steps {
                // Change to the Angular project directory
                dir('DevOps_Project_Front-20231016T100741Z-001(1)/DevOps_Project_Front') {
                    // Install dependencies
                    sh 'npm install'

                    // Build the Angular application
                    sh 'ng build --prod'
                }
            }
        }
       
         */
        stage('Deploy to Nexus') {
    steps {
         dir('DevOps_Project-20231016T100739Z-001/DevOps_Project') {
            sh 'mvn deploy -DskipTests'
                }        
            }
        }
         
         


      
    
    }
}

