pipeline {
    agent any 
    stages {
        stage('Stop container') { 
            steps {
                sh "docker-compose -f docker/docker-compose.yml down"
            }
        }
        stage('Test') { 
            steps {
                // 
                echo "=== TEST step ==="
            }
        }
        stage('=== Up new container ===') { 
            steps {
                echo "TEST deploy!"
                sh "docker-compose -f docker/docker-compose.yml up -d --build"
            }
        }
    }
}
