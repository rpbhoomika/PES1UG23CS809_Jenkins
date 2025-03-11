pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'g++ -o pes809-1 program.cpp' // Compile the C++ file
            }
        }

        stage('Test') {
            steps {
                sh './pes809' // Execute the compiled binary
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
