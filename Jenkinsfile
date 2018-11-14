properties([pipelineTriggers([githubPush()])])
node('linux') {
    git url: 'https://github.com/gernermc/java-project.git', branch: 'master'
    stage('Unit Tests') {
        env
        sh "ant -f test.xml -v"
    }
    stage('Build') {
        sh "ant -f build.xml -v"
    }
    stage('Deploy') {
        
    }
    stage('Report') {
        aws cloudformation describe-stack-resources --region us-east-1 --stack-name jenkins-stack
    }
}
