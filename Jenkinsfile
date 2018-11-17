pipeline {
    agent { label 'linux' }
    stages {
        stage('Unit Tests') {
            steps {
                git 'https://github.com/gernermc/java-project.git'
                sh "ant -f test.xml -v"
                junit 'reports/result.xml'
            }
        }
        stage('Build') {
            steps {
                sh "ant -f build.xml -v"
            }
        }
        stage('Deploy') {
            steps {
                s3Upload(file:"rectangle-${BUILD_NUMBER}.jar", bucket:"gernermc-assignment9", path:"/workspace/java-pipeline/dist/rectangle-${BUILD_NUMBER}.jar")
            }
        }
        stage('Report') {
            steps {
                sh "echo ${BUILD_NUMBER}"
            }
        }
    }
}
