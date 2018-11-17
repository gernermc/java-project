pipeline {
    agent { label 'linux' }
    git url: 'https://github.com/gernermc/java-project.git', branch: 'master'
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
