pipeline {
    agent any
    environment {
        DOCKER_TAG = getVersion()
    }
    stages {
        stage ('Clone Stage') {
            steps { 
                git 'https://github.com/ahmedKhlif/aston-villa-jenkins.git'
                sh 'echo Cloning repository completed.'
                sh 'echo $DOCKER_TAG'
            }
        }
        stage ('Docker Build') {
            steps {
                sh 'docker build -t ahmedkhlif/aston-villa:${DOCKER_TAG} .'
                sh 'echo Docker build completed.'
            }
        }
    }
}

def getVersion() {
    return sh(script: 'git rev-parse --short HEAD', returnStdout: true).trim()
}
