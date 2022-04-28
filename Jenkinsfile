#!groovy

stage('Checkout code') {
    node() {
        checkout scm
        sh "ls"
    }
}

stage('Check node version') {
    node() {
        sh "ls"
        sh "node -v"
        sh "npm -v"
    }
}

stage('Write and stash a file') {
    node() {
        sh 'echo "hello world!" > hello.txt'
        stash 'sources'
    }
}

stage('Read from stashed file') {
    node() {
        unstash 'sources'
        sh 'cat hello.txt'
    }
}

stage('Check AWS credentials') {
    node() {
        sh 'aws sts get-caller-identity'
    }
}
