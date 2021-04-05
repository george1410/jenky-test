pipeline {
    agent {
        docker { 
            image 'node:14-alpine'
            label 'ecs'
        }
    }
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
            }
        }
    }
}
