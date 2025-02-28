pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                 git branch:'main', url:'https://github.com/v-i-k-a-s-1-7/pep-exam.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-app .'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker stop flask-app || true'
                sh 'docker rm flask-app || true'
                sh 'docker run -d -p 5000:5000 --name flask-app flask-app'
            }
        }
    }
}
