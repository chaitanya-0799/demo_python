pipeline {
    agent any
    stages {
        stage('Gitcheckout'){
            steps {
                git branch: 'main', url: 'https://github.com/chaitanya-0799/demo_python.git'
            }
        }
        stage('pull'){
            steps {
                sh 'docker build -t python:latest -f build/Dockerfile .'
            }
        }

        
        stage('Deploy') {
            steps {
                sh 'docker stop demo-python || true'
                sh 'docker rm demo-python || true'
                sh 'docker run -itdp 800:5000 --name demo-python python:latest '
            }
        }
    }
}
