pipeline {
  agent any
  stages {
    stage('Check out code') {
      steps {
        git(url: 'https://github.com/mingnguyn/curriculum-app', branch: 'dev')
      }
    }

    stage('Logs') {
      steps {
        sh 'ls -la'
      }
    }

    stage('Build') {
      steps {
        sh '''
docker build -f curriculum-front/Dockerfile . '''
      }
    }

    stage('Log in to Dockehub') {
      environment {
        DOCKERHUB_USER = 'haiminh85'
        DOCKERHUB_PASSWORD = 'nhm08059x'
      }
      steps {
        sh 'docker login -u $DOCKERHUB_USER -p $DOCKERHUB_PASSWORD'
      }
    }

  }
}