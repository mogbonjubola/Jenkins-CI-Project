pipeline {
    agent any
    tools{
        maven "MAVEN3"
        jdk "OracleJDK8"
    }

    environment{
        SNAP_REPO = 'udemy-snapshot'
        NEXUS_USER = 'admin'
        NEXUS_PASS = 'Motunrayo@94'
        RELEASE_REPO = 'udemy-release'
        CENTRAL_REPO = 'udemy-maven-central'
        NEXUSIP = '52.90.172.209'
        NEXUSPORT = '8081' 
        NEXUS_GRP_REPO = 'udemy-maven-group'
        NEXUS_LOGIN = 'nexus_login'
    }
    stages {
        stage('Build'){
            steps {
                sh 'mvn -s settings.xml -DskipTests install'
            }
            post {
                success {
                    echo "Now Archiving."
                    archiveArtifacts artifacts: '**/*.war'
                }
            }
        }

        stage('Test'){
            steps {
                sh 'mvn -s settings.xml test'
            }

        }

        stage('Checkstyle Analysis'){
            steps {
                sh 'mvn -s settings.xml checkstyle:checkstyle'
            }
        }
    }
}