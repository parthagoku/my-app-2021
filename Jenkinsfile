node{
  stage('Scm checkout')
  {
    git 'https://github.com/parthagoku/my-app-2021'  
  }
  stage('compile-package')
  {
    def mvnHome = tool name: 'maven-3', type: 'maven'
    sh "${mvnHome}/bin/mvn package"
  }

  stage('Slack-notification')
  {
slackSend baseUrl: 'https://hooks.slack.com/services/', channel: ' #jenkins-pipeline-project2', color: 'good', 
  message: 'Welcome to Jenkins/Slack', tokenCredentialId: 'slack-demo', username: 'DevopsAspirant'
  }
  
}
