pipeline {
    agent any
    tools { nodejs "node" }
    triggers {
        githubPush()
    }
    stages {
        stage('Prepare') {
            steps {
                sh 'echo Log API_URL parameter'
                sh 'echo ${API_URL}'

                sh 'echo Check node version'
                sh 'node -v'

                sh 'echo Check yarn version'
                sh 'yarn -v'

                sh 'echo Install project dependencies'
                sh 'yarn'

                sh 'echo Check Angular version'
                sh 'yarn ng v'
            }
        }

        stage('Lint') {
            steps {
                sh 'yarn lint'
            }
        }

        stage('build') {
            steps {
                sh 'yarn build'
            }
        }
    }
}
