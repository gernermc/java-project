properties([pipelineTriggers([githubPush()])])
node('linux') {
    git url: 'https://github.com/gernermc/java-project.git', branch: 'master'
    stage('Unit Tests') {
        sh "ant -f test.xml -v"
    }
    stage('Build') {
        sh "ant -f build.xml -v"
    }
    stage('Deploy') {
    }
    stage('Report') {
    }
}
