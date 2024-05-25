pipeline {
    agent {
        label "docker-agent"
    }
    stages {
        stage('Install Docker Compose') {
            steps {
                script {
                    // Install Docker Compose
                    sh 'curl -L https://github.com/docker/compose/releases/download/2.27.1/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose'
                    sh 'chmod +x /usr/local/bin/docker-compose'
                }
            }
        }
        stage ('Run Docker Compose') {
            steps {
                // Run Docker Compose
                sh 'docker-compose up -d'
            }
        }
    }
}
