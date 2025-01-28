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
                sh 'docker stop python || true'
                sh 'docker rm python || true'
                sh 'docker run -itdp 800:5000 python:latest --name demo-python '
            }
        }
    }
}
