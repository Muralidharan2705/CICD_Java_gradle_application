pipeline{
    agent any
    stages{
        stage("Sonar_quality_check"){
            agent {
                docker {
                    image 'openjdk:17'
                }
             }
             steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar-login') {
                       sh "chmod +x gradlew"
                       sh "./gradlew sonarqube"
                    }
                }
                echo "========executing A========"
             }
            
        }
   }
 }