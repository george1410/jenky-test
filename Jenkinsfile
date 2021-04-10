pipeline {
    agent none
    stages {
        stage('Check node version') {
            agent { label 'ecs' }
            steps {
                sh 'node -v'
                sh 'npm -v'
            }
        }
        stage('Write and stash a file') {
            agent { label 'ecs' }
            steps {
                sh 'echo "hello world!" > hello.txt'
                stash 'sources'
            }
        }
        stage('Read from stashed file') {
            agent { label 'ecs' }
            steps {
                unstash 'sources'
                sh 'cat hello.txt'
            }
        }
        stage('Check AWS credentials') {
            agent { label 'ecs' }
            steps {
                sh 'aws sts get-caller-identity'
            }
        }
    }
}
