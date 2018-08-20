pipeline {
  agent any
  stages {
    stage('Example') {
      input {
        message 'Who to do it?'
        id 'Person'
        submitter 'admin'
        parameters {
          booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        }
      }
      steps {
        echo "Hello, ${PERSON}, nice to meet you."
        sh 'export PERSON=One'
        echo "${PERSON}"
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
    PERSON = 'Two'
  }
}