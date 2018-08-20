pipeline {
  agent any
  stages {
    stage('Example') {
      steps {
        echo "Hello, ${PERSON}, nice to meet you."
        input(message: 'go on?', id: 'test', ok: 'yes', submitter: 'admin', submitterParameter: 'test')
      }
    }
    stage('run') {
      when {
        environment ignoreCase: true, name: 'PERSON', value: 'One'
      }
      steps {
        echo 'SUCCESS'
        echo "${params.CHOICES}"
      }
    }
  }
  environment {
    PERSON = 'One'
  }
  parameters {
    choice(name: 'CHOICES', choices: '''one
two
three''', description: '')
  }
}