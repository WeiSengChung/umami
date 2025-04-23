pipeline {
    agent any

    environment {
        PATH = "C:\\Users\\user\\AppData\\Roaming\\npm;${env.PATH}"
    }

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
