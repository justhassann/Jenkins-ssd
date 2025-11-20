pipeline {
    agent any
    // THIS IS THE NEW TOOLS BLOCK
    tools {
        maven 'Maven' 
    }
    environment {
        NEW_VERSION = '1.3.0' 
    }
    stages {
        stage('Build') {
            steps {
                // THIS STAGE IS MODIFIED AGAIN
                echo 'Building Project'
                echo "Building version ${NEW_VERSION}"
                sh "mvn --version" 
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
