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
        echo 'Message to console'
      }
    }

    stage('Buzz When') {
      when {
        branch 'master'
      }
      steps {
        sh 'echo In master branch'
      }
    }

  }
}