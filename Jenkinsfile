pipeline {
  agent any
  stages {
    stage('stage1') {
      parallel {
        stage('stage1') {
          steps {
            sleep 1
          }
        }
        stage('stage2') {
          steps {
            sleep 2
          }
        }
      }
    }
  }
}