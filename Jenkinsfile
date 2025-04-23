pipeline {
    agent any

    tools {
        nodejs 'nodejs-22.13.1'
    }

    stages {
        stage('Install Dependencies') {
            steps {
                sh 'yarn install'
            }
        }

        stage('Build') {
            steps {
                sh 'yarn build'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'yarn test'
            }
        }
    }

    post {
        always {
            echo "Build completed using Node.js 22.13.1"
        }
    }
}