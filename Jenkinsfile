pipeline {
    agent any
    tools {
        maven 'Maven-3.9.9' // Use the name defined in Jenkins (case-sensitive)
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'
                echo 'Build Stage Successful'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
                echo 'Test Stage Successful'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deploy') {
            steps {
                sh 'mvn deploy'
                echo 'Deployment Successful'
            }
        }
    }
    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
