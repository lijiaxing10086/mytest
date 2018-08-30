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
        dir(path: '${WORKSPACE}/test') {
          sh '''ls -l
pwd'''
        }

        sh '''pwd
'''
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