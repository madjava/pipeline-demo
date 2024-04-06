pipeline {
  agent none
  stages {
    stage('Buzz Build') {
      agent {
        node {
          label 'docker-agent-alpine'
        }

      }
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

        stage('Buzz Python') {
          agent {
            node {
              label 'docker-agent-python'
            }

          }
          steps {
            sh 'print("Hello from Python")'
          }
        }

      }
    }

  }
}