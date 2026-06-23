pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Setup Python') {
            steps {
                bat 'python --version'
            }
        }
        stage('Build and Run') {
            steps {
                bat 'python app.py'
            }
        }
    }
    post {
        success { echo 'Build successful' }
        failure { echo 'Build failed' }
    }
}
