pipeline {
    agent {
        docker {
            image 'node:18' // Node 18 with default npm (v9), we upgrade it below
        }
    }

    stages {
        stage('Setup') {
            steps {
                sh 'npm install -g npm@10.8.2' // Upgrade npm to match your local version
            }
        }

        stage('Install') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Start') {
            steps {
                // If this is for testing (e.g., for `npm test`, not a prod server)
                sh 'npm start & sleep 5'
            }
        }
    }
}
