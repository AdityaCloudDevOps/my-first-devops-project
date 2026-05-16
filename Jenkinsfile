pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-nginx-app .'
            }
        }

        stage('Remove Old Container') {
            steps {
                sh 'docker rm -f mycontainer || true'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 8085:80 --name mycontainer my-nginx-app'
            }
        }

    }
}