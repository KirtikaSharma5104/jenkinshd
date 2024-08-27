pipeline {
    agent any

    environment {
        NODE_ENV = 'production'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from your Git repository
                git 'https://github.com/KirtikaSharma5104/jenkinshd.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                // Install npm dependencies using npm
                bat 'npm install'
            }
        }

        stage('Build') {
            steps {
                // Build the React application
                bat 'npm run build'
            }
        }

        stage('Test') {
            steps {
                // Run tests using Jest
                bat 'npm test -- --watchAll=false'
            }
        }

        stage('Deploy') {
            steps {
                // Placeholder for deployment commands
                echo 'Deploying the application...'
                // Example: Copy build files to a server
                // bat 'xcopy build\\* \\\\server\\path\\to\\deploy /E /Y'
            }
        }
    }

    post {
        always {
            // Clean up workspace after the build
            cleanWs()
        }
        success {
            echo 'Build, Test, and Deploy stages completed successfully.'
        }
        failure {
            echo 'Build, Test, or Deploy stages failed.'
        }
    }
}
