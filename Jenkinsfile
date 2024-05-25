pipeline {
    agent any
    environment {
        DOCKER_COMPOSE_VERSION = "2.27.1"
        DOCKER_COMPOSE_URL = "https://github.com/docker/compose/releases/download/${DOCKER_COMPOSE_VERSION}/docker-compose-Linux-x86_64"
    }
    stages {
        stage('Install Docker Compose') {
            steps {
                sh "curl -L ${DOCKER_COMPOSE_URL} -o docker-compose"
                sh "chmod +x docker-compose"
                sh "mv docker-compose /usr/local/bin/"
            }
        }
        stage('Run Docker Compose') {
            steps {
                sh "docker-compose up -d"
            }
        }
    }
}
