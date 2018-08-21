pipeline {
  agent any
  stages {
    stage('Example-1') {
      parallel {
        stage('Example-1') {
          steps {
            echo 'echo-1'
            input(message: 'GO ON?', id: 'TEST', ok: 'YES', submitter: 'admin', submitterParameter: 'test')
            sleep 3
          }
        }
        stage('Example-2') {
          steps {
            echo 'echo-2'
            sleep 4
          }
        }
        stage('Example-3') {
          steps {
            echo 'echo-3'
            sleep 15
          }
        }
      }
    }
    stage('Example-2') {
      when {
        environment ignoreCase: true, name: 'PERSON', value: 'One'
      }
      steps {
        echo 'SUCCESS'
      }
    }
  }
  environment {
    PERSON = 'One'
  }
}