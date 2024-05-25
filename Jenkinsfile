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
                    // Move Docker Compose to the home directory of the Jenkins user
                    sh 'mv docker-compose /home/jenkins'
                    // Add the directory containing Docker Compose to the PATH
                    sh 'export PATH=/home/jenkins:$PATH'
                }
            }
        }
        stage ('Run Docker Compose') {
            steps {
                // Run Docker Compose using the full path
                sh '/home/jenkins/docker-compose up -d'
            }
        }
    }
}
