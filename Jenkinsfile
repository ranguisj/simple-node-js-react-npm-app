pipeline {
  agent {
    docker {
      image 'node:18.17.1-alpine3.18'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('welcome') {
      steps {
        sh 'echo "coucou"'
      }
    }

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
        sh '''yarn global add firebase-tools
export PATH="$(yarn global bin):$PATH"
echo FIREBASE_TOKEN'''
      }
    }

  }
  environment {
    FIREBASE_TOKEN = '1//03RzgiQ-zEEKvCgYIARAAGAMSNwF-L9Ir30Kg_k9UP_HM9eRddtpGZJZt4u91OhTX6CsN2jL14vLq55RjotvktmJnXm7FcI8THA0'
  }
}