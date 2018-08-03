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
      steps {
        ws(dir: 'branch1') {
          sh 'pwd'
        }
        
      }
    }
  }
}