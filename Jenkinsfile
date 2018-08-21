pipeline {
  agent any
  stages {
    stage('Example') {
      steps {
        input(message: 'go on?', id: 'test', ok: 'yes', submitter: 'admin', submitterParameter: 'test')
        echo "${GIT_COMMIT}"
        echo "${GIT_URL}"
        echo "${GIT_BRANCH}"
      }
    }
    stage('run') {
      steps {
        echo 'SUCCESS'
      }
    }
  }
}