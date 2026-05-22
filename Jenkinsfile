pipeline {
    agent any

    stages {

        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }

            steps {

                sh '''
                    node --version
                    npm --version

                    npm install
                    npm run build

                    ls -la
                    ls -la build
                '''
            }
        }

        stage('Test') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }

            steps {

                sh '''
                    test -f build/index.html

                    echo "index.html exists"

                    npm test -- --watchAll=false
                '''
            }
        }
    }
}