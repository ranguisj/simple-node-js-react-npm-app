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
echo FIREBASE_TOKEN
firebase deploy --only hosting:testsimplereact --project ranguisj-5435f --token $FIREBASE_TOKEN'''
      }
    }

  }
  environment {
    FIREBASE_TOKEN = '1//03hcyPwc1ORKDCgYIARAAGAMSNwF-L9Ir-y_ceG-Zd8Qoxty_5J3FFYIsZvEAgBz-tXJiuvdo3ZqVgvXKtGjViBJ-omJKjVI96h8'
  }
}