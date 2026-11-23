pipeline {
  agent any

  environment {
    NODE_OPTIONS = '--max_old_space_size=4096'
  }

  stages {
    stage('Install') {
      steps {
        sh 'node --version && npm --version'
        sh 'npm install'
      }
    }

    stage('Lint') {
      steps {
        sh 'npm run lint'
      }
    }

    stage('Test') {
      steps {
        sh 'npm test'
      }
    }

    stage('Coding challenge consistency') {
      steps {
        sh 'npm run rsn'
      }
    }

    stage('Build') {
      steps {
        sh 'npm run build'
      }
    }
  }
}
