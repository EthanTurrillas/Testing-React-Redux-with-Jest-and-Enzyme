pipeline {
    agent any

    stages {
        stage('Checkout') {
            when {
                branch pattern: "feature.*", comparator: "REGEXP"
            }
            steps {
                checkout scm
            }
        }

        stage('Build') {
            when {
                branch pattern: "feature.*", comparator: "REGEXP"
            }
            steps {
                echo 'Building project...'
                sh 'npm install'
                sh 'npm run build'
            }
        }

        stage('Testing') {
            when {
                branch pattern: "feature.*", comparator: "REGEXP"
            }
            steps {
                echo 'Running tests...'
                sh 'npm test -- --coverage --watchAll=false'
            }
        }
    }
}
