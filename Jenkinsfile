properties([pipelineTriggers([githubPush()])])
node('linux') {
    git url: 'https://github.com/gernermc/infrastructure-pipeline.git', branch: 'master'
    stage('Test') {
        sh "env"
        }
        }
