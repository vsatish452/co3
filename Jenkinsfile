
pipeline {
    agent any

    options {
        timestamps()
    }

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code'
                checkout scm
            }
        }

        stage('Verify Environment') {
            steps {
                bat 'git --version'
                bat 'python --version'
            }
        }

        stage('Inspect Repository') {
            steps {
                bat 'dir'
                bat 'git log -1 --oneline'
            }
        }

        stage('CI Successful') {
            steps {
                echo 'GitHub source code validation completed'
            }
        }
    }

    post {
        success {
            echo 'CI pipeline completed successfully!'
        }

        failure {
            echo 'CI pipeline failed. Check the console output.'
        }
    }
}
