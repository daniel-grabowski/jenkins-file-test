pipeline {
    agent { docker { image 'node:18.10.0-alpine' } }
    stages {
        stage('NPM Install') {
            withEnv(["NPM_CONFIG_LOGLEVEL=warn"]) {
                sh 'npm install'
            }
        }

        stage('Lint') {
            sh 'ng lint'
        }

        stage('build') {
            steps {
                sh 'node --version'
                sh 'ng build'
            }
        }
    }
}
