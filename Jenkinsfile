pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t devops-app:latest .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker stop devops-container || true'
                sh 'docker rm devops-container || true'
                sh 'docker run -d --name devops-container -p 80:80 devops-app:latest'
            }
        }
    }
}
