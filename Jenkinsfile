pipeline {
  agent any
  stages {
    stage('Example') {
      parallel {
        stage('stage-1') {
          steps {
            echo 'SUCCESS'
          }
        }
        stage('stage-2') {
          steps {
            echo '123'
          }
        }
      }
    }
    stage('stage-2') {
      steps {
        echo '456'
      }
    }
  }
}