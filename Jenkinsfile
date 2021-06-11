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
  
  stage('sonar-Analysis')
  {
  def mvnHome = tool name: 'maven-3', type: 'maven'
    withSonarQubeEnv('sonar-7')
    {
    sh "${mvnHome}/bin/mvn sonar:sonar"
    }
  }

  stage('Slack-notification')
  {
slackSend baseUrl: 'https://hooks.slack.com/services/', channel: ' #jenkins-pipeline-project2', color: 'good', 
  message: 'Welcome to Jenkins/Slack', tokenCredentialId: 'slack-demo', username: 'DevopsAspirant'
  }
  
}
