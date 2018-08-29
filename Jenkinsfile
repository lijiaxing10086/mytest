pipeline {
  agent any
  stages {
    stage('stage-1') {
      steps {
        sh 'mkdir test1'
        sh 'cd ${WORKSPACE}/test1'
        sh 'pwd'
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