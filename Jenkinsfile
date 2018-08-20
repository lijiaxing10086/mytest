pipeline {
  agent any
  stages {
    stage('Example') {
      environment {
        TEST = '123'
      }
      input {
        message 'Who to do it?'
        id 'Person'
        submitter 'admin'
        parameters {
          string(name: 'PERSON', defaultValue: 'admin', description: 'Who to do it?')
        }
      }
      steps {
        echo "Hello, ${params.PERSON}, nice to meet you."
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