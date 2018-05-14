properties([pipelineTriggers([githubPush()])])

node('linux') {
    git credentialsId: 'github-creditial', url: 'https://github.com/AnakinTang/java-project.git'
    stage('Test') {
        sh "echo hello world"
        sh "ant -f test.xml -v"
        junit 'reports/result.xml' 
        
        withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'Jenkins-AWS', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
    aws cloudformation describe-stack-resources --region us-east-1 --stack-name jenkins
}

    }
}
