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
        beforeAgent true
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