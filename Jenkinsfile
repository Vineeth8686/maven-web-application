pipeline {
    agent none

    stages {
        stage("Build") {
            agent {
                docker {
                    image 'java:1.0'
                    label 'agent' // Use Maven image instead of Java
                }
            }
            steps {
                sh "mvn package"
            }
        }
    }
}