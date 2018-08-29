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
touch testfile
ls -l'''
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
        dir(path: '/home') {
          sh '''pwd
touch testfile2
ls -l
cd ..
ls -l
cd home 
ls -l
sleep 300'''
        }

      }
    }
  }
  environment {
    TEST1 = 'test1'
  }
}