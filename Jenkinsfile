#!groovy

stage('Checkout code') {
    node() {
        checkout scm
        sh "ls"
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
