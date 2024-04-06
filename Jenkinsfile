pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      steps {
        sh './build.sh'
      }
    }

    stage('Buzz Test') {
      parallel {
        stage('Buzz Test') {
          steps {
            sh './test-all.sh'
          }
        }

        stage('Testing B') {
          steps {
            sh '''sleep 10 


&&
echo done'''
          }
        }

      }
    }

  }
}