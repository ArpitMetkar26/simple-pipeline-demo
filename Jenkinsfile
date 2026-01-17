pipeline {
    agent any

    environment {
        APP_NAME = "simple-pipeline-demo"
    }

    stages {

        stage('Clone') {
            steps {
                echo "Source code already checked out by Declarative SCM"
                sh 'ls -la'
            }
        }

        stage('Build') {
            steps {
                echo "Building ${APP_NAME}"
               sh 'echo "Build successful" > build.txt'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests"
                echo "All tests passed"
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying ${APP_NAME}"
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: 'build.txt'
            echo "Pipeline executed successfully"
        }
    }
}
