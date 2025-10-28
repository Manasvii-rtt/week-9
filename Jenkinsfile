pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t registration:v1 .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                bat 'docker tag registration:v1 chandana1357/registration:v1'
                bat 'docker push chandana1357/registration:v1'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f C:/Users/chand/Downloads/week-9-main/week-9-main/deployment.yaml'
                bat 'kubectl apply -f C:/Users/chand/Downloads/week-9-main/week-9-main/service.yaml'
            }
        }
    }
}
