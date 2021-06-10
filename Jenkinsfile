node{
  stage('Scm checkout')
  {
    git 'https://github.com/parthagoku/my-app-2021'  
  }
  stage('compile-package')
  {
  sh 'mvn package'
  }
}
