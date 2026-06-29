pipeline {
    agent any

    tools {
        maven 'Maven3'
    }

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/Sagar242004/ExamMaven.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t exammaven .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run --rm exammaven'
            }
        }
    }
}