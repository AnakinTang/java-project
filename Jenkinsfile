properties([pipelineTriggers([githubPush()])])

node('linux') {
    git url: 'https://github.com/AnakinTang/java-project.git', branch: 'master'
    stage('Test') {
        sh "echo hello world"
        sh "ant -f test.xml -v"
        junit 'reports/result.xml' 

    }
}
