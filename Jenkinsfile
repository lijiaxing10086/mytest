pipeline {
  agent any
  stages {
    stage('Example') {
      steps {
        input(message: 'go on?', id: 'test', ok: 'yes', submitter: 'admin', submitterParameter: 'test')
        echo "${EXECUTOR_NUMBER}"
        echo "${BUILD_NUMBER}"
        echo "${CHANGE_ID}"
        echo "${CHANGE_URL}"
        echo "${CHANGE_TITLE}"
        echo "${BUILD_ID}"
        echo "${BUILD_DISPLAY_NAME}"
      }
    }
    stage('run') {
      steps {
        echo 'SUCCESS'
      }
    }
  }
}