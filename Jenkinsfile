pipeline {
    agent none

    stages {
        stage("Build") {
            agent {
                docker {
                    image 'maven3.8.2'
                    label 'agent' // Use Maven image instead of Java
                }
            }
            steps {
                sh "mvn package"
            }
        }
    }
}