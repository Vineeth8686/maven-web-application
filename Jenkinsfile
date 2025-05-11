pipeline {
    agent none

    stages {
        stage("Clean") {
            agent {
                docker {
                    image 'java:1.0'
                    label 'agent' // Use Maven image instead of Java
                    reuseNode true
                }
            }
            steps {
                sh "mvn clean"
                stash includes: 'target/*.jar', name: 'built-artifact'
            }
        }
         stage("Package") {
            agent {
                docker {
                    image 'java:1.0'
                    label 'agent' // Use Maven image instead of Java
                    
                }
            }
            steps {
                sh "mvn package"
                stash includes: 'target/*.war', name: 'maven-war-artifact'
            }
        }
    }
}