
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Source code is available in the workspace.'
                bat 'dir'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the sample application...'
                bat 'if exist app.txt (echo Build successful) else (echo app.txt missing & exit /b 1)'
            }
        }

        stage('Test') {
            steps {
                echo 'Running automated tests...'
                bat 'findstr /C:"Hello from Assignment 7!" app.txt'
                echo 'All tests passed!'
            }
        }
    }

    post {
        success {
            echo 'CI Pipeline completed successfully!'
        }
        failure {
            echo 'CI Pipeline failed. Check the stage logs.'
        }
        always {
            echo 'Pipeline execution finished.'
        }
    }
}
