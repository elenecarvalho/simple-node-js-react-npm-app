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

    stage('installer') {
      steps {
        sh 'npm install'
      }
    }

    stage('build') {
      steps {
        sh 'npm run build'
      }
    }

    stage('deploy') {
      steps {
        sh '''yarn global add firebase-tools




'''
        sh 'export PATH="$(yarn global bin):$PATH"'
        sh 'firebase deploy --only hosting:briefcicdcarvalhoelene --project docker-2cdd0 --token $FIREBASE_TOKEN'
      }
    }

  }
  environment {
    FIREBASE_TOKEN = '1//03OSy3hxT_U5tCgYIARAAGAMSNwF-L9IrmNb6n5RZ_8HWZ77yFVlB_6cFFwYG4aQ3cVecjTPTXRzeFMceSKlmPZ2p46qPq1j88oY'
  }
}