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
                sh '''
                for i in {1..5}; do
                  curl http://localhost:8000/httpbin/get && break
                  echo "Retrying..."
                  sleep 5
                done
                '''
            }
        }

    }
}
