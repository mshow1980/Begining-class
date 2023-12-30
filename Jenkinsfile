pipeline{
    agent any
    stages{
        stage("sonar quality cherck"){
            agent {
                docker {
                    image 'openjdk:11'
                }
            }
            steps{
              script{
                withSonarQubeEnv(credentialsId: 'SOnar-token') {
                    sh 'chmod +x gradlew'
                    sh './gradlew sonarqube'
                }
              }
         }
      }
    }
}