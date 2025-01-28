pipeline {
    agent any
    stages {
        stage('Gitcheckout'){
            steps {
                git branch: 'main', url: 'https://github.com/chaitanya-0799/demo_python.git'
            }
        }
        stage('Remove-previous-image') {
            steps {
                sh '''
                    docker ps -aq | xargs docker stop --time=0
                    docker ps -aq | xargs docker rm
                    docker images -q | xargs docker rmi
                '''
            }
        }
        stage('pull'){
            steps {
                sh 'docker build -t ypp:lat -f build/Dockerfile .'
            }
        }

        
        stage('Deploy') {
            steps {
                sh 'docker run -itdp 800:5000 ypp:lat --name demo-python '
            }
        }
    }
}
