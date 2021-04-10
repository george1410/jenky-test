#!groovy

stage('Checkout code') {
    node('ecs') {
        checkout scm
    }
}

stage('Check node version') {
    node('ecs') {
        sh "node -v"
        sh "npm -v"
    }
}

stage('Write and stash a file') {
    node('ecs') {
        sh 'echo "hello world!" > hello.txt'
        stash 'sources'
    }
}

stage('Read from stashed file') {
    node('ecs') {
        unstash 'sources'
        sh 'cat hello.txt'
    }
}

stage('Check AWS credentials') {
    node('ecs') {
        sh 'aws sts get-caller-identity'
    }
}
