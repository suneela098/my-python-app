pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh '''
                docker build -t my-python-app:latest .
                '''
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker stop my-python-app || true
                docker rm my-python-app || true
                docker run -d -p 5000:5000 --name my-python-app my-python-app:latest
                '''
            }
        }
    }
}
