pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }

    stages {
        // Specify various stage with in stages

        // stage 1. Build
        stage ('Build'){
            steps {
                sh 'mvn clean install package'
            }
        }

        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing......'

            }
        }

        // Stage3 : Publish the artifacts to Nexus

        stage ('Publish to Nexus'){
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'BasanDevOpsLab', classifier: '', file: 'target/BasanDevOpsLab-0.0.7-SNAPSHOT.war', type: 'war']], credentialsId: '825f68cd-c74f-4665-858b-49f1f300a1e3', groupId: 'com.basansdevopslab', nexusUrl: '172.20.10.92:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'BasansDevOpsLab-SNAPSHOT', version: '0.0.7-SNAPSHOT'
            }
        }

        // Stage3 : Publish the source code to Sonarqube
        stage ('Deploy'){
            steps {
                echo ' Building......'
            } 
        }
 
    }

}