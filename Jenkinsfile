node() {
    stage('checkout code') {
    checkout([$class: 'GitSCM', branches: [[name: 'develop']], extensions: [], userRemoteConfigs: [[credentialsId: 'Github', url: 'git@github.com:sagidevops/CodeWithDanDockerServices.git']]])
    }
    stage('build') {
    sh '''export APP_ENV=development && \
    export DOCKER_ACCT=sagie350 && \
    docker-compose build'''
    }
    stage('run test') {
    sh '''export APP_ENV=development && \
    export DOCKER_ACCT=sagie350 && \
    docker-compose up -d'''
    }
}
