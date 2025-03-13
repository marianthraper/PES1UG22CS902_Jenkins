pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                build 'PES1UG22CS902-1'
                sh 'g++ main.cpp -o output'
                echo 'Build Stage Successful'
            }
        }

        stage('Test') {
            steps {
                sh './opt'
                echo 'Test Stage successful'
            }
        }

        stage('Deploy') {
            steps {
               
                echo 'Deployment Successful'
            }
        }
    }

    post {
        failure {
            echo "Pipeline failed"
        }
        success {
            echo "Pipeline completed successfully!"
        }
    }
}
