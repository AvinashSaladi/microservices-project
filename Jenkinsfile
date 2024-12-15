pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t avinash1836/microservices:loadgeneratorservice .'
            }
        }
        stage('Push'){
            steps{
                script{
                    withDockerRegistry(credentialsId: 'docerhub-credentials') {
                        sh 'docker push avinash1836/microservices:loadgeneratorservice'
                    }
                }
            }
        }
    }
}
