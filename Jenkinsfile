pipeline {
  agent any
  stages {
    stage('Example') {
      steps {
        echo "Hello, ${PERSON}, nice to meet you."
      }
    }
    stage('run') {
      when {
        beforeAgent true
        environment ignoreCase: true, name: 'PERSION', value: 'One'
      }
      steps {
        echo 'SUCCESS'
      }
    }
  }
}