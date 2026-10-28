pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *')
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code from GitHub'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application'
                bat 'echo Build Successful'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing the application'
                bat 'echo Tests Passed'
            }
        }
    }
}
