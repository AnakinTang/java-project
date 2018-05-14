properties([pipelineTriggers([githubPush()])])

node('linux') {
    git credentialsId: 'github-creditial', url: 'https://github.com/AnakinTang/java-project.git'
    stage('Test') {
        sh "echo hello world"
        sh "ant -f test.xml -v"
        junit 'reports/result.xml' 

    }
}
