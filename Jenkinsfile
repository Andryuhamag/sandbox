pipeline {
    agent any 
    stages {
        stage('=== Stop docker-compose and remove images ===') { 
            steps {
                //sh "docker-compose -f /home/andy/projects/nginx-docker-ci-project/docker-compose.yml down"
                //sh "docker images | grep 'my-nginx' | awk '{print \$1}' | xargs docker rmi"
                sh "docker-compose -f /home/andy/projects/sandbox/docker/docker-compose.yml down"
                sh "docker images | grep 'my-nginx' | awk '{print \$1}' | xargs docker rmi"
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
                //sh "cd /home/andy/projects/nginx-docker-ci-project"
                //sh "docker-compose -f /home/andy/projects/nginx-docker-ci-project/docker-compose.yml up -d"
                sh "docker-compose -f /home/andy/projects/sandbox/docker/docker-compose.yml up -d"
            }
        }
    }
}
