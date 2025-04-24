pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Test') {
            agent{
                docker{
                    image 'node:22'
                    args '-u root:root'
                }
            }
            steps {
                sh '''
                    ls -la
                    node -v
                    npm -v
                    npm install
                    npm run build
                '''
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}