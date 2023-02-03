pipeline{
    agent any
      tools {
        maven 'Maven-tool'
            }

    stages{
        stage('Build'){
         steps{
             sh script: 'mvn clean install'
            }
        }

    }


}
