pipeline {
    agent none

    stages {
        stage("Smoke test") {
            agent {
                docker {
                    image 'java:1.0'
                    label 'agent' // Use Maven image instead of Java
                    reuseNode true
                }
            }
            steps {
                sh "mvn clean"
            }
        }
         stage("Package") {
            agent {
                docker {
                    image 'java:1.0'
                    label 'agent' // Use Maven image instead of Java
                    args '-v /home/azureuser/.m2:/root/.m2'
                }
            }
            steps {
                sh "mvn package"
                stash includes: 'target/*.war', name: 'maven-war-artifact'
            }
        }
        stage("UnStaching a File"){
            agent {
                docker {
                    image 'java:1.0'
                    label 'agent' // Use Maven image instead of Java
                    
                }
                }
            steps{
                unstash name: "maven-war-artifact" , message: "UnStashing the file"
                archiveArtifacts artifacts: '**/*.war', followSymlinks: false
            }
        }

    }
}