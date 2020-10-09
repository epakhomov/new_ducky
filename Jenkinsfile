pipeline {

    agent {
        node {
            label 'master'
        }
    }

    options {
        buildDiscarder logRotator( 
                    daysToKeepStr: '16', 
                    numToKeepStr: '10'
            )
    }

    stages {
        

        stage('Code Checkout') {
            steps {
                checkout([
                    $class: 'GitSCM', 
                    branches: [[name: '*/main']], 
                    userRemoteConfigs: [[url: 'https://github.com/spring-projects/spring-petclinic.git']]
                ])
            }
        }



        stage('Build Deploy Code') {
            when {
                branch 'develop'
            }
            steps {
                echo 'RUNNING DETECT'
        synopsys_detect '--blackduck.url=https://poc43.blackduck.synopsys.com --detect.project.name=ducky-crm --detect.project.version.name=develop --blackduck.trust.cert=true --detect.excluded.detector.types=MAVEN --blackduck.api.token=NWFlZjAxN2EtNTBjYS00ZTgwLWJiYmYtYWI4ZTJkMGM4MDkwOmE1ZTAxZTk5LTRlYzUtNDIyNy05ZjBiLTgxN2M0ODk2YjJiNA=='
            }
        }

    }   
}
