pipeline {
    agent any
    tools { nodejs "node" }
    stages {
        stage('Prepare') {
            steps {
                sh 'echo Check node, yarn and npm version'
                sh 'node -v'
                npm command: '-v'
                yarn command: '-v'

                sh 'nvm install v16.15.1'
                sh 'nvm use v16.15.1'
                sh 'nvm alias default v16.15.1'

                sh 'echo Install @angular/cli'
                npm command: 'install -g @angular/cli'

                yarn command: 'install'
            }
        }

        stage('Lint') {
            steps {
                yarn command: 'lint'
            }
        }

        stage('build') {
            steps {
                yarn command: 'build'
            }
        }
    }
}
