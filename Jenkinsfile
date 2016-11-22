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
    stage('Forked tests') {
      steps {
            parallel(
                firstBlock: {
                  echo 'first block'
                  sh 'pwd'
                  sh 'sleep 20'
                },
                secondBlock: {
                  echo 'second block'
                  sh 'pwd'
                  sh 'sleep 10'
                }
            )
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
            parallel(
                firstBlock: {
                  echo 'first block'
                  sh 'pwd'
                  sh 'sleep 10'
                },
                secondBlock: {
                  echo 'second block'
                  sh 'pwd'
                  sh 'sleep 10'
                }
                },
                thirdBlock: {
                  echo 'second block'
                  sh 'pwd'
                  sh 'sleep 20'
                }
            )
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
