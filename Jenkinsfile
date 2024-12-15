pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8s-token', namespace: 'project', serverUrl: 'https://C06DF0B3050A333948DB78BEB238D0E2.gr7.ap-south-1.eks.amazonaws.com']]) {
                    sh "kubectl apply -f deployment-service.yml"
                    
                }
            }
        }
        
        stage('verify Deployment') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8s-token', namespace: 'project', serverUrl: 'https://C06DF0B3050A333948DB78BEB238D0E2.gr7.ap-south-1.eks.amazonaws.com']]) {
                    sh "kubectl get svc -n project"
                }
            }
        }
    }
}
