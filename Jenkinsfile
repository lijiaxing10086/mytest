pipeline {
  agent any
  stages {
    stage('Example') {
      steps {
        input(message: 'go on?', id: 'test', ok: 'yes', submitter: 'admin', submitterParameter: 'test')
        echo "${EXECUTOR_NUMBER}"
        echo '%{BUILD_NUMBER}'
      }
    }
    stage('run') {
      steps {
        echo 'SUCCESS'
      }
    }
  }
}