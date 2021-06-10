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
}
