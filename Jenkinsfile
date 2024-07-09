pipeline {
      agent { label 'jenkins-agent' }
      tools {
           jdk 'JDK17'
           maven 'Maven3'
        }
      stages {
           stage("Cleanup Workspace"){
              steps{
              cleanWs()
              }
       }
          stage("Checkout from SCM"){
             steps{
                script{
                    git branch :'main'
                    credentialsId : '@github'
                    url : 'https://@github.com/AwsDevops2024/mybranch.git'
                }
          }
      }
         stage("Build Application"){
            steps{
              sh "mvn clean package"
           }
      }
         stage("Test Application"){
           steps{
              sh "mvn test"
          }
      }
   }
}
