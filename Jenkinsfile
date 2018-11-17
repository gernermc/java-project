pipeline {
    agent { label 'linux' }
    stages {
        stage('Unit Tests') {
            sh "ant -f test.xml -v"
            junit 'reports/result.xml'
        }
        stage('Build') {
            sh "ant -f build.xml -v"
        }
        stage('Deploy') {
            sh "echo ${BUILD_NUMBER}"
        }
        stage('Report') {
        }
    }
}
