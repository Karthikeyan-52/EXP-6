
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
                echo 'Building Java application...'
                bat 'javac -d . Hello.java'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing Java application...'
                bat 'java exp6.Hello'
            }
        }

        stage('Docker Build') {
            steps {
                echo 'Building Docker image...'
                bat 'docker build -t devops-app:latest .'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Application deployment completed!'
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
