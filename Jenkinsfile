node() {
    environment {
        APP_ENV = "development"
        DOCKER_ACCT= "sagie350"
    }
    stage('checkout code') {
    checkout([$class: 'GitSCM', branches: [[name: 'develop']], extensions: [], userRemoteConfigs: [[credentialsId: 'Github', url: 'git@github.com:sagidevops/CodeWithDanDockerServices.git']]])
    }
    stage('build') {
    sh'''docker-compose build'''
    }
    stage('run test') {
    sh '''docker-compose up'''
    }
}