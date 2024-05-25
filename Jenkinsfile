pipeline {
    agent {
        label "docker-agent"
    }
    stages {
        stage('Install Docker Compose') {
            steps {
                script {
                    // Install Docker Compose in the current workspace directory
                    sh 'curl -L https://github.com/docker/compose/releases/download/2.27.1/docker-compose-Linux-x86_64 -o docker-compose'
                    sh 'chmod +x docker-compose'
                    // Move Docker Compose to a directory accessible by Jenkins
                    sh 'mv docker-compose $HOME'
                    // Add the directory containing Docker Compose to the PATH
                    sh 'export PATH=$HOME:$PATH'
                }
            }
        }
        stage ('Run Docker Compose') {
            steps {
                // Run Docker Compose
                sh '$HOME/docker-compose up -d'
            }
        }
    }
}
