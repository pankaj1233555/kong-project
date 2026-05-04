pipeline {
    agent any

    stages {

        stage('Deploy Kong') {
            steps {
                sh 'docker-compose down'
                sh 'docker-compose up -d'
            }
        }

        stage('Test API') {
            steps {
                sh 'curl http://localhost:8000/httpbin/get'
            }
        }
    }
}
