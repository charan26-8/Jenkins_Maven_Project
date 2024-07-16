pipeline {
    agent any

    tools {
        maven 'Maven' // Use the exact name configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/charan26-8/Jenkins_Maven_Project' // Replace with your repository URL
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Package') {
            steps {
                bat 'mvn package'
            }
        }
    }

    post {
        always {
            junit 'target/surefire-reports/*.xml'
        }
    }
}

