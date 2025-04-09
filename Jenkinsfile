pipeline {
    agent {
        docker {
            image 'node:18'
        }
    }

    stages {
        stage('Install') {
            steps {
                sh 'npm install'
            }
        }

        stage('Start') {
            steps {
                sh 'npm start &'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
    }
}
