pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'g++ -o pes809 program.cpp || exit 1'
                sh 'ls -l'  // Check if binary exists
            }
        }

        stage('Test') {
            steps {
                sh 'chmod +x pes809'
                sh './pes809'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment step (mock for now)'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
