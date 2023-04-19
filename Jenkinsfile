pipeline {
    agent { docker { image 'node:18.10.0-alpine3.15' } }
    stages {
        stage('YARN Install') {
            steps {
                sh 'yarn install'
            }
        }

        stage('Lint') {
            steps {
                sh 'ng lint'
            }
        }

        stage('build') {
            steps {
                sh 'node --version'
                sh 'ng build'
            }
        }
    }
}
