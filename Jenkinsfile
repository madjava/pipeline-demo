pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      steps {
        sh './build.sh'
      }
    }

    stage('Buzz Test') {
      steps {
        sh './test-all.sh'
      }
    }

  }
}