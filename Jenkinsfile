pipeline {
    agent none

    stages {
        stage("Build") {
            agent {
                docker {
                    image 'java:latest'
                    label 'agent' // Use Maven image instead of Java
                }
            }
            steps {
                sh "mvn package"
            }
        }
    }
}