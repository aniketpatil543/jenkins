pipeline {
    agent any

    tools {
        maven 'maven3'
        jdk 'jdk24'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', credentialsId: 'ee49e449-b9d3-40a5-b852-ea6fb355891a', url: 'https://github.com/aniketpatil543/jenkins.git'
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

        stage('Deploy to Test Environment') {
    steps {
        echo 'Deploying to test environment...'
    }
}

    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
