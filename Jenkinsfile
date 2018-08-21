pipeline {
  agent any
  stages {
    stage('Example') {
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
          environment {
            TEST = '123'
          }
          steps {
            echo "Hello, ${params.PERSON}, nice to meet you."
            sh 'export PERSON=One'
            echo "${PERSON}"
          }
        }
        stage('Example-2') {
          steps {
            echo 'echo-1'
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
        echo "${params.CHOICES[1]}"
      }
    }
  }
  environment {
    PERSON = 'One'
  }
}