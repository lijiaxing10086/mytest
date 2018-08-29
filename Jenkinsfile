pipeline {
  agent any
  stages {
    stage('stage-1') {
      environment {
        TEST2 = 'test2'
      }
      steps {
        sh '''echo ${TEST1}
echo ${TEST2}'''
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

        error '2'
      }
    }
  }
  environment {
    TEST1 = 'test1'
  }
}