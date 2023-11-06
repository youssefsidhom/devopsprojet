
stage('Build Frontend') {
            steps {
                // Add steps to build the Angular frontend here
                dir('frontend-directory') {  // Navigate to your frontend directory
                    sh 'npm install'        // Install project dependencies
                    sh 'ng build --prod'    // Build the Angular application for production
                }
            }
        }
