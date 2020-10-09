pipeline {
    agent {
        node {
            label 'master'
        }
    }
    
    stages {
        stage('Build') {
            steps {
                sh '/var/jenkins_home/maven/apache-maven-3.6.3/bin/mvn clean package'
            }
        }
        
        
        
    
        stage('Deliver for development') {
            when {
                branch 'davemeurer-patch-2' 
            }
            steps {
                echo 'RUNNING DETECT'
        synopsys_detect '--blackduck.url=https://poc43.blackduck.synopsys.com --detect.project.name=ducky-crm --detect.project.version.name=davemeurer-patch-2 --blackduck.trust.cert=true --detect.excluded.detector.types=MAVEN --blackduck.api.token=NWFlZjAxN2EtNTBjYS00ZTgwLWJiYmYtYWI4ZTJkMGM4MDkwOmE1ZTAxZTk5LTRlYzUtNDIyNy05ZjBiLTgxN2M0ODk2YjJiNA=='
            }
        }
        
        stage('Deploy for production') {
            when {
                branch 'davemeurer-patch-3'  
            }
            steps {
                echo 'RUNNING DETECT'
        synopsys_detect '--blackduck.url=https://poc43.blackduck.synopsys.com --detect.project.name=ducky-crm --detect.project.version.name=davemeurer-patch-3 --blackduck.trust.cert=true --detect.excluded.detector.types=MAVEN --blackduck.api.token=NWFlZjAxN2EtNTBjYS00ZTgwLWJiYmYtYWI4ZTJkMGM4MDkwOmE1ZTAxZTk5LTRlYzUtNDIyNy05ZjBiLTgxN2M0ODk2YjJiNA=='
            }
        }
    }
}
