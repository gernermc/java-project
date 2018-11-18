pipeline {
    agent { label 'linux' }
    stages {
        stage('Unit Tests') {
            steps {
                git credentialsId: 'github-credentials', url: 'https://github.com/gernermc/java-project.git'
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
                sh "aws s3 cp rectangle-${BUILD_NUMBER}.jar s3://gernermc-assignment9/rectangle-${BUILD_NUMBER}.jar"
            }
        }
        stage('Report') {
            steps {
                withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'jenkins-aws', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
                    sh "echo ${BUILD_NUMBER}"
                }
                
            }
        }
    }
}
