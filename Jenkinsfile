pipeline {
  agent any
  stages {
    stage('stage-1') {
      steps {
        sh 'mkdir test1'
        sh '''cd ${WORKSPACE}/test1
pwd'''
        sh 'pwd'
        sh(returnStatus: true, script: 'exit 2')
      }
    }
    stage('stage-2') {
      steps {
        echo '456'
        dir(path: '/test1') {
          sh 'pwd'
        }

      }
    }
  }
}