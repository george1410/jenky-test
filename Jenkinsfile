#!groovy

stage('Checkout code') {
    node('ecs') {
        checkout scm
        sh "ls"
    }
}

stage('Say Hi') {
    ecsNode {
        helloGeorge()
    }
}

stage('Check node version') {
    ecsNode {
        sh "ls"
        sh "node -v"
        sh "npm -v"
    }
}

stage('Write and stash a file') {
    ecsNode {
        sh 'echo "hello world!" > hello.txt'
        stash 'sources'
    }
}

stage('Read from stashed file') {
    ecsNode {
        unstash 'sources'
        sh 'cat hello.txt'
    }
}

stage('Check AWS credentials') {
    ecsNode {
        sh 'aws sts get-caller-identity'
    }
}
