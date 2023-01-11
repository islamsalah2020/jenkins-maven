pipeline {

    agent {  
        docker { image 'maven:3.5.4-jdk-8'
                 args '-v /root/.m2:/root/.m2'
        }
    }
   
    environment {
        NEXUS_VERSION = "nexus3"
        NEXUS_PROTOCOL = "http"
        NEXUS_URL = "3.138.114.25:8081"
        NEXUS_REPOSITORY = "maven-nexus-repo"
        NEXUS_CREDENTIAL_ID = "nexus-cred-new"
    }

    
    stages {
        stage('Build Maven') {
            steps{

                sh "mvn -Dmaven.test.failure.ignore=true clean package"
                
            }
        }
    }
    
}
