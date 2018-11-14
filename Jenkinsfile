properties([pipelineTriggers([githubPush()])])
node('linux') {
    git url: 'https://github.com/gernermc/java-project.git', branch: 'master'
    stage('Test') {
        sh "env"
    }
    stage('Unit Tests') {
        sh "ant -f test.xml -v"
    }
}
