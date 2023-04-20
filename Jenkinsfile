pipeline {
    docker { image 'node:18.16-alpine' }
    stages {
        stage('Prepare') {
            steps {
                sh 'Check node, yarn and npm version'
                sh 'node -v'
                npm command: '-v'
                yarn command: '-v'

                yarn command: 'install'
            }
        }

        stage('Lint') {
            steps {
                sh 'ng lint'
            }
        }

        stage('build') {
            steps {
                sh 'ng build'
            }
        }
    }
}
