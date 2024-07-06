pipeline {
    agent { label 'agent-label' }
    
    stages {
        stage('Hello Kubernetes Deploy') {
            steps {
                script {
                    // Print out environment variables for debugging
                    sh 'env | sort'
                    
                    // Execute kubectl commands with the correct path to your config file
                    withKubeConfig(credentialsId: 'kube-id') {
                        sh 'kubectl version --client'
                        sh 'kubectl get nodes'
                        sh 'kubectl get pods --all-namespaces'
                    }
                }
            }
        }
    }
}
