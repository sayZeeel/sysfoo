pipeline {
  agent any

  triggers { pollSCM('H/2 * * * *') }
  
  tools {
      maven 'Maven 3.6.3'
  } 
  
  stages{
      stage("Build"){
          steps{
              echo 'compile maven app'
              sh 'mvn compile'
          }
      }
      stage("Test"){
          steps{
              echo 'test maven app'
              sh 'mvn clean test'
          }
      }
      stage("Package"){
          steps{
              echo 'package maven app'
              sh 'mvn package -DskipTests'

          }
      }
  }

  post{
    always{
        echo 'This pipeline is completed..'
    }
  }
}