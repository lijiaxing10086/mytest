pipeline {
  agent any
  stages {
    stage('stage1') {
      parallel {
        stage('stage1') {
          steps {
            sleep 1
          }
        }
        stage('') {
          steps {
            echo 'aaa'
            input(message: 'input1', id: 'input1', ok: 'input1')
            echo 'bbb'
            input(message: 'input2', id: 'input2', ok: 'input2')
          }
        }
      }
    }
    stage('stage3') {
      steps {
        sleep 1
      }
    }
    stage('test') {
      steps {
        timeout(time: 20, activity: true, unit: 'SECONDS') {
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