pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
	stage('Debug PATH') {
    	    steps {
        	bat 'echo %PATH%'
        	bat 'where python || echo Python not in PATH'
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
