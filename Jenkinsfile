pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/amitojha18/myapp.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myapp .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker rm -f mycontainer || true'
            }
        }

        stage('Run New Container') {
            steps {
                sh 'docker run -d -p 80:80 --name mycontainer myapp'
            }
        }
    }
}
