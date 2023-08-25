pipeline {
    agent {
        docker {
            image 'node:18.17.1-alpine3.18' 
            args '-p 3000:3000' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
                sh 'ls' // Cette ligne exécute "ls helloworld" dans le répertoire de travail
            }
        }
    }
}
