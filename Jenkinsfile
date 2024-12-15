pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                dir('src') {
                    sh 'docker build -t avinash1836/microservices:cartservice .'
                }
            }
        }

        stage('Push Docker Image') {
            steps {
                script {
                    // Use Docker registry with credentials for authentication
                    withDockerRegistry(credentialsId: 'docerhub-credentials') {
                        sh 'docker push avinash1836/microservices:cartservice'
                    }
                }
            }
        }
    }
}
