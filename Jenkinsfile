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
                dir('DevOps_Project-20231016T100739Z-001/DevOps_Project') {
                    // Use Maven to build the application
                    sh 'mvn clean package'
                }
            }
        }
         stage('Unit Tests') {
steps {
dir ('DevOps_Project-20231016T100739Z-001/DevOps_Project'){
sh 'mvn test'
}
}
        }
                stage('Build Angular Frontend') {
        steps {
            script {
                // Set the PATH to include the directory where npm and node are installed
                def nodeBin = tool 'NodeJS' // Replace with the actual tool name
                def nodePath = "${nodeBin}/bin"
                env.PATH = "${nodePath}:${env.PATH}"
                // Navigate to the Angular project directory
                dir('DevOps_Project_Front-20231016T100741Z-001(1)/DevOps_Project_Front') {
                    // Install project dependencies
                    sh 'npm install'
        
                    // Build the Angular application
                    sh 'npm run build'
                }
            }
        }
    }
                    stage('Deploy to Nexus') {
    steps {
         dir('DevOps_Project-20231016T100739Z-001/DevOps_Project') {
            sh 'mvn deploy -DskipTests'
                }        
            }
        }

        stage('SonarQube Scan') {
            steps {
                          dir('DevOps_Project-20231016T100739Z-001/DevOps_Project') {
                    // Use Maven to build the application
                      sh 'mvn sonar:sonar -Dsonar.login=squ_99d938e3a7314f9bce2219987669c2a5f47a3ac7'
                }
             
            }
        }
       
 
        
        stage('Grafana/prometheus') {
            steps {
                sh 'docker start 82bf015e0b20'
                sh 'docker start d25ce5289b9e'
            }
        }

       
 

         /*


       tage('Build and Push Backend Image') {
             steps {
                  script {
                    dir('DevOps_Project-20231016T100739Z-001/DevOps_Project') {
                            sh "docker login -u bouakroucha -p dckr_pat_2K37V8hZv0EnZ6AU8YMixrSlZuw"
                            // Build your Docker image
                            sh "docker build -t bouakroucha/devopsbackendproject:1.0 ."
                            // Push the image
                            sh "docker push bouakroucha/devopsbackendproject:1.0"
                        }
                    }
                }
         }










         
        stage('Nexus mvn deploy'){
            steps {
                 dir('DevOps_Project-20231016T100739Z-001/DevOps_Project') {
                
                sh "mvn deploy"
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
        
        
   
        
        
        stage('Build and Push Backend Image') {
             steps {
                  script {
                    dir('back') {
                            sh "docker login -u achref5 -p \$docker_cred"
                            // Build your Docker image
                            sh "docker build -t achref/devopsbackendproject:1.0 ."
                            // Push the image
                            sh "docker push achref/devopsbackendproject:1.0"
                }
            }
        }
    }
        */
         
         


      
    
    }
}

