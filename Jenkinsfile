
pipeline {
    agent any

    stages {
        stage('Check Kubernetes') {
            steps {
                bat 'kubectl --kubeconfig="C:\\Users\\LENOVO\\.kube\\config" get nodes'
            }
        }

        stage('Deploy Application') {
            steps {
                bat 'kubectl --kubeconfig="C:\\Users\\LENOVO\\.kube\\config" apply -f app.yaml'
            }
        }

        stage('Verify Deployment') {
            steps {
                bat 'kubectl --kubeconfig="C:\\Users\\LENOVO\\.kube\\config" rollout status deployment/exam-web'
                bat 'kubectl --kubeconfig="C:\\Users\\LENOVO\\.kube\\config" get deployments,pods,services'
            }
        }
    }
}
