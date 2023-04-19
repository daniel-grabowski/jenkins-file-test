pipeline {
    agent any
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
