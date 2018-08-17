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
        input(message: 'input sth', id: '123', ok: '25', submitter: 'admin', submitterParameter: 'test-1')
      }
    }
    stage('stage3') {
      steps {
        sleep 1
      }
    }
  }
}