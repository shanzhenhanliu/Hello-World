pipeline {
  agent {
    docker {
      args '-p 3000:3000'
      image 'node:6-alpine'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }

    stage('Test') {
      agent any
      environment {
        CI = 'true'
      }
      steps {
        sh './root/scripts/ping_test.sh'
      }
    }

  }
}