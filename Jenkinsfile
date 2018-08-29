pipeline {
  agent any
  stages {
    stage('stage-1') {
      environment {
        TEST1 = 'test4'
      }
      parallel {
        stage('stage-1') {
          environment {
            TEST2 = 'test2'
            TEST1 = 'test3'
          }
          steps {
            sh '''echo ${TEST1}
echo ${TEST2}
ls -l
mkdir test1
cd test1
touch testfile'''
            sh 'pwd'
            sh(returnStatus: true, script: 'ls -l')
          }
        }
        stage('error') {
          steps {
            sh 'echo ${TEST1}'
          }
        }
      }
    }
    stage('stage-2') {
      steps {
        echo '456'
        dir(path: '/test1') {
          sh '''pwd
ls'''
        }

      }
    }
  }
  environment {
    TEST1 = 'test1'
  }
}