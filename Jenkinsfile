pipeline {
  agent any
  stages {
    stage('Example') {
      steps {
        input(message: 'go on?', id: 'test', ok: 'yes', submitter: 'admin', submitterParameter: 'test')
        echo "${computer.name}"
        echo "${computer.jnlpmac} "
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