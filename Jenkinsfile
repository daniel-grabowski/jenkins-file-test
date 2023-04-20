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
