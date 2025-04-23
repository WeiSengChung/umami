pipeline {
    agent any

    stages {
        stage('Check Yarn Path') {
            steps {
                bat 'where yarn'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'yarn install'
            }
        }

        stage('Prepare Environment') {
            steps {
                writeFile file: '.env', text: 'DATABASE_URL=mysql://root:@localhost:3306/umami'
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
        success{
            echo "Build succeeded"
            deleteDir()
        }
    }
}
