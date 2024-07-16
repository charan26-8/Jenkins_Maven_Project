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
                bat '''
                    echo "Running mvn clean compile"
                    mvn clean compile -e -X
                '''
            }
        }

        stage('Test') {
            steps {
                bat '''
                    echo "Running mvn test"
                    mvn test -e -X
                '''
            }
        }

        stage('Package') {
            steps {
                bat '''
                    echo "Running mvn package"
                    mvn package -e -X
                '''
            }
        }
    }

    post {
        always {
            echo "Collecting test results"
            junit 'target/surefire-reports/*.xml'
        }
    }
}
