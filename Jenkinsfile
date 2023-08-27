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
yarn global add firebase-tools
export PATH="$(yarn global bin):$PATH"
firebase login:ci --no-localhost --token "AIzaSyAJ-JoV-kYTH70bcVcMKM3G_rb2o4PQU-w"'''
      }
    }

  }
}