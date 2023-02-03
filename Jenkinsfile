pipeline{
    agent any
    tools {
      maven 'Maven-3.8.7'
          }

    stages{
        stage('Build'){
         steps{
             sh script: 'mvn clean install'
            }
        }

    }


}
