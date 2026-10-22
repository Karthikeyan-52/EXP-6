
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Source code checkout completed.'
            }
        }

        stage('Build') {
            steps {
                echo 'Building Java application...'
                bat 'if not exist build mkdir build'
                bat 'javac -d build Hello.java'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing Java application...'
                bat 'java -cp build exp6.Hello'
            }
        }

        stage('Docker Build') {
            steps {
                echo 'Building Docker image...'

                bat '"C:\\Users\\Karthikeyan SN\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" --version'

                bat '"C:\\Users\\Karthikeyan SN\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" build -t devops-app:latest .'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Docker image built successfully.'
                echo 'Application is ready for deployment.'
            }
        }
    }

    post {
        success {
            echo 'DevOps CI/CD Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed. Check Console Output for errors.'
        }

        always {
            echo 'Pipeline execution completed.'
        }
    }
}
