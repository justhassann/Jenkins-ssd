pipeline {
    agent any
    // THIS IS THE NEW ENVIRONMENT BLOCK
    environment {
        NEW_VERSION = '1.3.0' 
    }
    stages {
        stage('Build') {
            steps {
                // THESE STEPS ARE MODIFIED
                echo 'Building Project'
                echo "Building version ${NEW_VERSION}" 
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    post { 
        always { 
            echo 'Post build condition running'
        }
        failure {
            echo 'Post Action if Build Failed'
        }
    }
}
