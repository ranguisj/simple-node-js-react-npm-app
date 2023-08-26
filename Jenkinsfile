pipeline {
  agent {
    docker {
      image 'node:18.17.1-alpine3.18'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('Install') {
      steps {
        sh 'npm install'
      }
    }

    stage('Build') {
      steps {
        sh 'npm run build'
      }
    }

    stage('Deploy') {
      steps {
        sh '''ls
sudo npm install -g firebase-tools'''
      }
    }

  }
}