pipeline { 
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker build -t artistrk/checkoutservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentials: 'docker-cred', toolName: 'docker') {
                        sh "docker push artistrk/checkoutservice:latest "
                    }
                }
            }
        }
    }
}
