pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                bat '''
                docker build -t my-python-app:latest .
                '''
            }
        }

        stage('Run Container') {
            steps {
                bat '''
                docker stop my-python-app || exit 0
                docker rm my-python-app || exit 0
                docker run -d -p 5000:5000 --name my-python-app my-python-app:latest
                '''
            }
        }
    }
}
