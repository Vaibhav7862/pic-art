 pipeline {
    agent any 
  stages {
    stage('Startup') {
      steps {
        script {
          sh 'npm install'
        }
      }
    }
    stage('Test') {
      steps {
        script {
          sh 'npm test a || exit'
          sh 'npm test q'
        }
      }
      post {
        always {
          junit 'output/coverage/junit/junit.xml'
        }
      }
    }
    stage('Build') {
      steps {
        script {
          sh 'npm run build'
        }
      }
    }
  }
} 