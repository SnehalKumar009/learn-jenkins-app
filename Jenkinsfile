pipeline {
    agent any

    stages {
        stage('w/o docker') {
            steps {
                sh 'echo "Hello Without Docker"'
                sh 'touch container_without_docker.txt'
            }
        }
        
        stage('w/ docker'){
            agent {
                docker {
                    image 'nginx:latest'
                    reuseNode true
                }
            }
            steps{
                sh 'echo "Hello With Docker"'
                sh 'uname -a'
                sh 'touch container_with_docker.txt'
            }
        }
    }
}