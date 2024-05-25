pipeline {
    agent any

    stages {
        stage('Install Docker Compose') {
            steps {
                script {
                    sh '''
                        curl -L https://github.com/docker/compose/releases/download/2.27.1/docker-compose-Linux-x86_64 -o docker-compose
                        chmod +x docker-compose
                        mv docker-compose /home/jenkins/
                        export PATH=$PATH:/home/jenkins/
                    '''
                }
            }
        }

        stage('Run Docker Compose') {
            steps {
                sh 'docker-compose up -d'
            }
        }
    }
}
