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

        stage('Buzz Python') {
          agent {
            docker {
              label 'docker-agent-python' // both label and image
              image 'devopsjourney1/myjenkinsagents:python'
            }
          }
          steps {
            sh 'python print("Hello from Python")'
          }
        }
      }
    }
  }
}
