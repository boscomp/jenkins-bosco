pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t web-bosco .'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker stop web-bosco-container || true'
                sh 'docker rm web-bosco-container || true'
                sh 'docker run -d --name web-bosco-container -p 80:80 web-bosco'
            }
        }
    }
}
