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
        ws(dir: '/test1') {
          sh '''touch testfile
pwd
ls -l
cd ..
ls -l
sleep 200'''
        }

      }
    }
  }
  environment {
    TEST1 = 'test1'
  }
}