pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Build') {
            steps {
                echo 'Building the project...'
                sh 'npm install'
                sh 'npm run build'  
            }
        }

        stage('Testing') {
            steps {
                echo 'Running tests...'
                sh 'npm test -- --coverage --watchAll=false' 
            }
        }
    }

    when {
        branch pattern: "feature.*", comparator: "REGEXP"
    }
}
