pipeline {
  agent any
  stages {
    stage('stage1') {
      steps {
        sleep 1
      }
    }
    stage('stage3') {
      steps {
        sleep 1
      }
    }
    stage('test') {
      steps {
        timeout(time: 20, activity: true) {
          input(message: 'need user admin permission', id: 'test', ok: 'permit', submitter: 'admin', submitterParameter: 'yes')
          sleep 10
        }

      }
    }
    stage('sleep') {
      steps {
        sleep 5
      }
    }
  }
}