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
                sh 'docker build -t ypp:lat -f /build/Dockerfile .'
            }
        }
        
        stage('Deploy') {
            steps {
                sh 'docker run -itdp 800:5000 ypp:lat'
            }
        }
    }
}
