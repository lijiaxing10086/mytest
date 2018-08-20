pipeline {
  agent any
  stages {
    stage('stage1') {
      parallel {
        stage('s-1-1') {
          steps {
            echo 'aaa'
          }
        }
        stage('s-1-2') {
          steps {
            echo 'aaa'
            input(message: 'input1', id: 'input1', ok: 'input1')
            echo 'bbb'
            input(message: 'input2', id: 'input2', ok: 'input2')
            echo '333'
          }
        }
      }
    }
  }
}