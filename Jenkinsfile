pipeline {
  agent any
  stages {
    stage('stage1') {
      steps {
        sleep 1
      }
    }
    stage('stage2') {
      parallel {
        stage('stage2') {
          steps {
            sleep 1
            sh 'ls'
          }
        }
        stage('aaaa') {
          steps {
            sh 'ls '
            sh 'ls 2'
          }
        }
      }
    }
  }
}