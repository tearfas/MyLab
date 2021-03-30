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
                nexusArtifactUploader artifacts: [[artifactId: 'brightdevopslab', classifier: 'war', file: 'target/brightdevopslab-0.0.77-SNAPSHOT.war', type: '']], credentialsId: 'ccc703e4-638c-44ae-a24a-bd67aa0bde20', groupId: 'com.brightdevopslab', nexusUrl: '92.168.1.217:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'BrightDevopsLab-SNAPSHOT', version: '0.0.77-SNAPSHOT'
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
