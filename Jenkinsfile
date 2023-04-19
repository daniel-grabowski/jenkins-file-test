pipeline {
    agent any
    stages {
        stage('Prepare') {
            steps {
                sh 'npm install -g @angular/cli'
                sh 'npm install -g yarn'
            }
        }
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
