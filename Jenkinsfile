//pipeline {
//    agent { label 'ecs' }
//    stages {
//        stage('Check node version') {
//            steps {
//                sh 'node -v'
//                sh 'npm -v'
//            }
//        }
//        stage('Write and stash a file') {
//            steps {
//                sh 'echo "hello world!" > hello.txt'
//                stash 'sources'
//            }
//        }
//        stage('Read from stashed file') {
//            steps {
//                unstash 'sources'
//                sh 'cat hello.txt'
//            }
//        }
//        stage('Check AWS credentials') {
//            steps {
//                sh 'aws sts get-caller-identity'
//            }
//        }
//    }
//}


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
