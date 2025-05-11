pipeline{
    agent none
    stages{  
        stage("Build"){
            agent {
             docker {
                label "Docker-Host"
                image 'java:latest'
             }
            steps{
            sh "mvn package"
            }
        }
    }
    }
}