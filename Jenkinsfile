pipeline {
    agent any

    environment {
        APP_NAME = "simple-pipeline-demo"
    }

    stages {

        stage('Clone') {
            steps {
                echo "Cloning repository for ${APP_NAME}"
                git 'https://github.com/ArpitMetkar26/simple-pipeline-demo.git'
            }
        }

        stage('Build') {
            steps {
                echo "Building application..."
                echo "Build successful" > build.txt
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                echo "All tests passed"
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying ${APP_NAME}..."
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: 'build.txt'
            echo "Pipeline completed successfully"
        }
    }
}
