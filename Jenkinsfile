pipeline {
    agent any
    // THIS IS THE NEW PARAMETERS BLOCK
    parameters {
        string(name: 'VERSION', defaultValue: '1.1.0', description: 'version to deploy on prod')
        choice(name: 'VERSION_CHOICES', choices:['1.1.0', '1.2.0', '1.3.0'], description:'')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }
    tools {
        maven 'Maven' 
    }
    environment {
        NEW_VERSION = '1.3.0' 
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building Project'
                echo "Building version ${NEW_VERSION}"
                sh "mvn --version" 
            }
        }
        // THIS STAGE IS NOW MODIFIED WITH A 'when' BLOCK
        stage('Test') {
            when {
                expression { params.executeTests == true } 
            }
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
