pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build: validating files'
                bat 'dir'
            }
        }

        stage('Test') {
            steps {
                echo 'Test: checking index.html'
                bat 'if not exist index.html exit 1'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying to IIS'
                bat '''
                xcopy index.html "C:\\inetpub\\wwwroot\\" /Y
                '''
            }
        }
    }
}
