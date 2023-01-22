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
    success{
            emailext to: "divyarani0911@gmail.com, kavyasrinigowda@gmail.com,shravanbhat.sb@gmail.com",
            subject: "jenkins build:${currentBuild.currentResult}",
            body: "Project Name: ${env.JOB_NAME}\nBuild: #${env.BUILD_NUMBER}\nBuild Status: ${currentBuild.currentResult}\nNote:Kindly donot reply to this email as it is automated"
            attachLog: true
                   
        }
    failure{
            emailext to: "divyarani0911@gmail.com, kavyasrinigowda@gmail.com,shravanbhat.sb@gmail.com",
            subject: "jenkins build:${currentBuild.currentResult}",
            body: "Project Name: ${env.JOB_NAME}\nBuild: #${env.BUILD_NUMBER}\nBuild Status: ${currentBuild.currentResult}\nMore Info can be found here: ${env.BUILD_URL}\nNote:Kindly donot reply to this email as it is automated"
            attachLog: true
        }
    }
}
