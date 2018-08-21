pipeline {
  agent any
  stages {
    stage('Example') {
      parallel {
        stage('Example-1') {
          steps {
            echo 'echo-1'
          }
        }
        stage('Example-2') {
          steps {
            waitUntil() {
              sleep 8
            }

          }
        }
      }
    }
    stage('run') {
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