#!groovy

stage('Checkout code') {
    node() {
        checkout scm
        sh "ls"
    }
}

stage('Say hello') {
    node() {
        echo 'Hello world!'
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
