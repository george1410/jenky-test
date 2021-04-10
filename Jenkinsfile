pipeline {
    agent {
        label 'ecs'
    }
    stages {
        stage('Check node version') {
            steps {
                sh 'node -v'
                sh 'npm -v'
            }
        }
        stage('Check AWS credentials') {
            steps {
                sh 'aws sts get-caller-identity'
            }
        }
    }
}
