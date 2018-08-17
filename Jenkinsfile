pipeline {
  agent any
  stages {
    stage('stage1') {
      steps {
        sleep 1
      }
    }
    stage('stage2') {
      steps {
        input(message: '需要admin用户的批准', id: '123', ok: '批准', submitter: 'admin', submitterParameter: 'test-1')
      }
    }
    stage('stage3') {
      steps {
        sleep 1
      }
    }
  }
}
