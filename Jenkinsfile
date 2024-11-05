pipeline {
    agent any
    tools { nodejs "node" }
    stages {
        stage('Prepare') {
            steps {
                sh 'echo Log GIT_BRANCH'
                sh 'echo ${GIT_BRANCH}'
    
                sh 'echo test'
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
    post {
        success {
            echo 'I succeeded!'
        }
        unstable {
            echo 'I am unstable :/'
        }
        failure {
            echo 'I failed :('
        }
        changed {
            echo 'Things were different before...'
        }
        always {
            echo 'One way or another, I have finished'
            deleteDir() /* clean up our workspace */
        }
    }
}
