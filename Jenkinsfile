
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Source code checkout completed'
            }
        }

        stage('Build') {
            steps {
                bat 'javac Hello.java'
            }
        }

        stage('Test') {
            steps {
                bat 'java Hello'
            }
        }

        stage('Docker Build') {
            steps {
                bat 'docker build -t devops-app:latest .'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Application container image created successfully'
            }
        }
    }

    post {
        success {
            echo 'DevOps Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check Console Output.'
        }
    }
}
