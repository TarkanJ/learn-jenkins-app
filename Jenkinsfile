pipeline {
    agent any

    environment {
        npm_config_cache = "${WORKSPACE}/.npm"
    }

    stages {

        stage('Install') {
            steps {

                sh 'rm -rf node_modules'

                sh 'npm ci'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
    }
}