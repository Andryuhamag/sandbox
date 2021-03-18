pipeline {
    agent any
    //triggers { pollSCM('*/5 * * * *') }
    options {
        buildDiscarder(logRotator(numToKeepStr: '5', artifactNumToKeepStr: '5'))
        timestamps()
    }
    stages {
        stage('Stop docker-compose') { 
            steps {
                sh "docker-compose -f docker/docker-compose.yml down"
            }
        }
        stage('Test') { 
            steps {
                // 
                echo "TEST step"
            }
        }
        stage('Start docker-compose') { 
            steps {
                echo "TEST deploy!"
                sh "docker-compose -f docker/docker-compose.yml up -d --build"
            }
        }
    }
}
