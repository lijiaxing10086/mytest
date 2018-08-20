pipeline {
  agent any
  stages {
    stage('Example') {
      input {
        message 'Should we continue?'
        id 'Yes, we should.'
        submitter 'alice,bob'
        parameters {
          string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
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