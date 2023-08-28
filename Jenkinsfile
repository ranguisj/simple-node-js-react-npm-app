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

  }
  environment {
    FIREBASE_TOKEN = '1//03RzgiQ-zEEKvCgYIARAAGAMSNwF-L9Ir30Kg_k9UP_HM9eRddtpGZJZt4u91OhTX6CsN2jL14vLq55RjotvktmJnXm7FcI8THA0'
  }
}