pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'echo building'
      }
    }
    stage('deploy') {
      steps {
        checkpoint 'ready to deploy'
        sh 'echo deploying'
      }
    }
    stage('verify') {
      steps {
        checkpoint 'verify deployment'
        sh 'echo verifying deployment'
      }
    }
    stage('blue<-->green') {
      steps {
        checkpoint 'activate deployment'
        sh 'echo switching blue and green'
      }
    }
  }
}
