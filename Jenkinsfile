pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                dir('src') {
                    sh 'docker build -t avinash1836/microservices:cartservice:${BUILD_NUMBER} .'
                }
            }
        }

        stage('Push Docker Image') {
            steps {
                script {
                    // Use Docker registry with credentials for authentication
                    withDockerRegistry(credentialsId: 'dockerhub-credentials') {
                        sh 'docker push avinash1836/microservices:cartservice:${BUILD_NUMBER}'
                    }
                }
            }
        }
    }
}
