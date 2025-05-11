pipeline{
    agent none
    stages{  
        stage("Build"){
             agent{
            label "agent"
            image 'java:latest'
             }
            steps{
            sh "mvn package"
            }
        }
    }
}