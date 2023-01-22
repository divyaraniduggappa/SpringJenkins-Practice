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
  post{
  changed{
            emailext to: "divyarani0911@gmail.com",
            subject: "jenkins build:${currentBuild.currentResult}: ${env.JOB_NAME}",
            body: "${currentBuild.currentResult}: Job ${env.JOB_NAME}\nMore Info can be found here: ${env.BUILD_URL}"
        }
    }
}
