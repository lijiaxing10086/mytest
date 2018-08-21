pipeline {
  agent any
  stages {
    stage('Example-1') {
      input {
        message 'Who to do it?'
        id 'Person'
        submitter 'admin'
        parameters {
          string(name: 'PERSON', defaultValue: 'admin', description: 'Who to do it?')
        }
      }
      parallel {
        stage('Example-1') {
          steps {
            echo 'echo-1'
          }
        }
        stage('Example-1') {
          steps {
            echo 'echo-2'
          }
        }
        stage('Example-1') {
          steps {
            echo 'echo-3'
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