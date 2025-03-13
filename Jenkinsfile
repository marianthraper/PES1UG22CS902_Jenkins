pipeline {
    agent any

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
                echo 'Test Stage successful'
                post{
                  always{
                    junit 'target/surefire-reports/*.xml'
                  }
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
            echo "Pipeline failed"
        }
        success {
            echo "Pipeline completed successfully!"
        }
    }
}
