pipeline {
  agent any
  stages {
    stage('Example') {
      parallel {
        stage('Example') {
          environment {
            TEST = '123'
          }
          steps {
            echo "Hello, ${params.PERSON}, nice to meet you."
            sh 'export PERSON=One'
            echo "${PERSON}"
          }
        }
        stage('Example') {
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
      }
    }
  }
  environment {
    PERSON = 'One'
  }
}