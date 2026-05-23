stage('Build') {
    agent {
        docker {
            image 'node:18-alpine'
            reuseNode true
        }
    }

    steps {
        sh '''
            pwd
            ls -la

            node --version
            npm --version

            cat package.json

            npm ci

            ls -la node_modules/.bin || true

            npm run build
        '''
    }
}