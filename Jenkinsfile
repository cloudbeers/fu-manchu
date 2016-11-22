pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'echo building'
        sh 'make'
        sh 'echo build complete'
      }
    }
    stage('Stage') {
      steps {
        checkpoint 'ready to deploy'
        sh 'echo deploying'
      }
    }
    stage('Verify') {
      steps {
        checkpoint 'verify deployment'
        sh 'echo verifying deployment'
      }
    }
    stage('Deploy') {
      steps {
        checkpoint 'activate deployment'
        sh 'echo switching blue and green'
      }
    }
  }
}
