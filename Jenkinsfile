pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/DevBhalodiya/CICD_Demo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t nodeapp:latest .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker run -d -p 8080:8080 nodeapp:latest'
            }
        }
    }
}
