pipeline {
    agent any
    environment {
        KUBECONFIG = "/etc/rancher/k3s/k3s.yaml"  // Hoặc "/var/lib/jenkins/.kube/config" nếu dùng bản sao
    }
    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/luannv35/k3s-configs.git'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f ./'
            }
        }
    }
}
