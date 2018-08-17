pipeline {
  agent any
  stages {
    stage('stage1') {
      steps {
        sh 'mkdir branch1'
        sh 'mkdir branch2'
      }
    }
    stage('stage2') {
      parallel {
        stage('stage2-1') {
          steps {
            sh 'ls -l'
          }
        }
        stage('stage2-2') {
          steps {
            sleep 10
          }
        }
      }
    }
    stage('stage3') {
      steps {
        sleep 1
      }
    }
  }
}