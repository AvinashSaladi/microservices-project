pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t avinash1836/microservices:shippingservice .'
            }
        }
        stage('Push'){
            steps{
                withDockerRegistry(credentialsId: 'docerhub-credentials') {
                    sh 'docker push avinash1836/microservices:shippingservice '
                }
            }
        }
    }
}
