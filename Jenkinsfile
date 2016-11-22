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
  }
}
