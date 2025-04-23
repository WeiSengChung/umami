pipeline {
    agent any

    environment {
        SKIP_DB_CHECK = '1'
    }

    tools {
        nodejs 'nodejs-22.13.1'
    }

    stages {
        stage('Install Dependencies') {
            steps {
                sh 'npm install --global yarn'
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