pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                bat 'yarn install'
            }
        }

        stage('Build') {
            steps {
                bat 'yarn build'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'yarn test'
            }
        }
    }

    post {
        always {
            echo "Build completed using Node.js 22.13.1"
        }
    }
}