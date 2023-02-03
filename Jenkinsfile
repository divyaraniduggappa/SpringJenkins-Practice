pipeline {
  agent {
    label "java"
        }
  stages {
    stage('checkout-scm') {
      steps{
        git credentialsId: 'git-hub-pwd', url: 'https://github.com/divyaraniduggappa/SpringJenkins-Practice.git'
      }
    }
    stage(maven) {
      steps{
        sh 'mvn clean install'
      }
    }
  }
  
}