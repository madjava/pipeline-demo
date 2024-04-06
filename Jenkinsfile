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
            echo 'Meesage to console'
          }
        }

        stage('Buzz Python') {
          agent {
            docker {
              label 'docker-agent-python'
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