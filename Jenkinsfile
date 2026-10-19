pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code...'
                checkout scm
            }
        }
        stage('Validate') {
            steps {
                echo 'Validating website...'
                sh 'ls -la'
                sh 'cat index.html'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying to Nginx...'
                sh 'sudo cp index.html /var/www/html/'
                sh 'sudo systemctl reload nginx'
                echo 'Deployment Successful!'
            }
        }
    }
}
