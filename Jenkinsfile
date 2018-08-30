pipeline {
  agent any
  stages {
    stage('dir') {
      steps {
        sh '''mkdir test
cd test 
touch testfile'''
      }
    }
    stage('ls -1') {
      steps {
        sh '''ls -l
cd test
ls -l'''
        sh '''ls -l
cd ..
cd ${WORKSPACE}/test
ls -l'''
      }
    }
    stage('ls -2') {
      steps {
        ws(dir: 'workspace') {
          sh '''pwd
ls -l
cd ..
ls -l'''
        }

      }
    }
  }
  environment {
    TEST1 = 'test1'
  }
  parameters {
    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
  }
}