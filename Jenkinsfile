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
        sh '''cd test
ls -l'''
        sh '''cd {WORKSPACE}/test
ls -l'''
      }
    }
    stage('ls -2') {
      steps {
        dir(path: '/home') {
          sh 'ls -l'
          sh '''cd jenkins
ls -l
'''
          sh '''cd jenkins/workspace/
ls -l
cd test
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