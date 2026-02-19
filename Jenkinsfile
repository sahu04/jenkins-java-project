pipeline {
    agent any
   
    stages {
        stage('checkout') {
            steps {
                git 'https://github.com/sahu04/jenkins-java-project.git'
            }
        }
        stage('build') {
            steps {
                sh 'mvn clean package'
            }
        }
   
        stage('artifact upload') {
            steps {
               nexusArtifactUploader artifacts: [[artifactId: 'NETFLIX', classifier: '', file: 'target/NETFLIX-1.2.2.war', type: 'war']], credentialsId: 'nexus', groupId: 'in.RAHAM', nexusUrl: '18.144.59.39:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'testrepository', version: '1.2.2'
            }
        }
        
    }    
    
}  
