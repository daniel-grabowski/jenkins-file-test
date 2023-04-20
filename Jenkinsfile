pipeline {
    agent any
    tools { nodejs "node" }
    stages {
        stage('Prepare') {
            steps {
                sh 'echo Cleanup workspace'
                cleanWs()

                sh 'echo Log API_URL parameter'
                sh '${API_URL}'

                sh 'echo Check node version'
                sh 'node -v'

                sh 'echo Check npm version'
                npm command: '-v'

                sh 'echo Check yarn version'
                yarn command: '-v'

                sh 'echo Install project dependencies'
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
