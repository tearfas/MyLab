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
                echo 'testing......'

            }
        }
        //Stage 3: Publish to nexus
        stage ('Publish To Nexus') {
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'brightdevopslab', classifier: '', file: 'target/brightdevopslab-0.0.7-SNAPSHOT.war', type: 'war']], credentialsId: '5c98ee06-f735-4b4b-8a9e-142d0b151fdf', groupId: 'com.brightdevopslab', nexusUrl: '192.168.1.217:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'BrightDevopsLab-SNAPSHOT', version: '0.0.7-SNAPSHOT'
            }
        }
        // Stage 4 : Publish the source code to Sonarqube
        stage ('Deploy') {
            steps {
                echo 'Deploying to Prod...... '
            }
        } 
    }

}
