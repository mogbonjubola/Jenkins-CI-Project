pipeline {
    agent any
    tools{
        maven "MAVEN3"
        jdk "OracleKDK8"
    }

    environment{
        SNAP_REPO = 'udemy-snapshot'
        NEXUS_USER = 'admin'
        NEXUS-PASSWORD = 'Motunrayo@94'
        RELEASE_REPO = 'udemy-release'
        CENTRAL_REPO = 'udemy-maven-central'
        NEXUSIP = '172.31.21.138'
        NEXUSPORT = '8081' 
        NEXUS_GRP_REPO = 'udemy-maven-group'
        NEXUS_LOGIN = 'nexus_login'
    }
    stages {
        stage('Build'){
            steps {
                sh 'mvn -s settings.xml -DskipTests install'
            }
        }
    }
}