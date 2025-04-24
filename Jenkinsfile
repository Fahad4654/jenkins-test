pipeline {
    agent any

    stages {
        stage('Build') {
            agent{
                docker{
                    image 'node:22'
                    args '-u root:root'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls -la
                    node -v
                    npm -v
                    npm install
                    npm run build
                    ls -la
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