pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Run Application') {
            steps {
                bat 'python app.py'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t devops-practical-3 .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker run --rm devops-practical-3'
            }
        }
    }

    post {
        success {
            echo 'CI/CD Pipeline completed successfully!'
        }

        failure {
            echo 'CI/CD Pipeline failed!'
        }
    }
}
