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
                ls -la
                node --version
                npm --version
                sudo chown -R 1001:1001 "/.npm"
                npm ci
                npm run build
                ls -la
            '''
            }    
        }
       
    }
}