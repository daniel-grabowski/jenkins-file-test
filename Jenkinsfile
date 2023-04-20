pipeline {
    agent any
    stages {
        stage('Prepare') {
            steps {
                npm command: 'install -g @angular/cli'
                npm command: 'install -g yarn'

                sh 'echo Check node and npm version'
                sh 'node -v'
                npm command: '-v'

                yarn command: 'install'
                yarn command: '-v'
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
