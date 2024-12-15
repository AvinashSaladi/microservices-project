pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t avinash1836/microservices:currencyservice .'
            }
        }
        stage('Push'){
            steps{
                withDockerRegistry(credentialsId: 'docerhub-credentials') {
                    sh 'docker push avinash1836/microservices:currencyservice'
                }
            }
        }
    }
}
