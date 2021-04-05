pipeline {
    agent {
        label 'ecs'
    }
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
                sh 'curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"'
                sh 'unzip awscliv2.zip'
                sh 'sudo ./aws/install'
                sh 'aws sts get-caller-identity'
            }
        }
    }
}
