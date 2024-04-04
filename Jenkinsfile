pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      steps {
        sh './build.sh'
        archiveArtifacts(artifacts: 'packaged.zip', fingerprint: true)
      }
    }

    stage('Buzz Test') {
      steps {
        sh './test-all.sh'
      }
    }

  }
}