pipeline {

    agent {
        node {
            label 'master'
        }
    }

    stages {
        

        stage('Code Checkout') {
            steps {
                    
        git 'https://github.com/epakhomov/new_ducky.git'
    
            }
        }



        stage('Build Deploy Code') {
            when {
                branch 'davemeurer-patch-1'
            }
            steps {
                echo 'RUNNING DETECT'
        synopsys_detect '--blackduck.url=https://poc43.blackduck.synopsys.com --detect.project.name=ducky-crm2 --detect.project.version.name=davemeurer-patch-2 --blackduck.trust.cert=true --detect.excluded.detector.types=MAVEN --blackduck.api.token=NWFlZjAxN2EtNTBjYS00ZTgwLWJiYmYtYWI4ZTJkMGM4MDkwOmE1ZTAxZTk5LTRlYzUtNDIyNy05ZjBiLTgxN2M0ODk2YjJiNA=='
            }
        }

    }   
}
