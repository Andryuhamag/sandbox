pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                sh "docker-compose -f /home/andy/projects/nginx-docker-ci-project/docker-compose.yml down"
                sh "docker images | grep 'my-nginx' | awk '{print \$1}' | xargs docker rmi"
            }
        }
        stage('Test') { 
            steps {
                // 
                echo "TEST step!"
            }
        }
        stage('Deploy') { 
            steps {
                echo "TEST deploy!"
                //sh "cd /home/andy/projects/nginx-docker-ci-project"
                sh "docker-compose -f /home/andy/projects/nginx-docker-ci-project/docker-compose.yml up -d"
            }
        }
    }
}
