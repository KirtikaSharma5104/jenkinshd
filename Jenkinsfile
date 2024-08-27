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
                // Install npm dependencies
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                // Build the React application
                sh 'npm run build'
            }
        }

        stage('Test') {
            steps {
                // Run tests using Jest
                sh 'npm test -- --watchAll=false'
            }
        }

        stage('Deploy') {
            steps {
                // In a real scenario, this might deploy to a server or hosting service
                echo 'Deploying the application...'
                // Example: Copy build files to a web server (This is a placeholder)
                // sh 'scp -r build/* user@server:/path/to/deploy/'
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

