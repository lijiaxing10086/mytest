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
        dir(path: '/home') {
          sh '''touch testfile
cd ..
ls -l
pwd
cd home@tmp
ls -l
cd ..
cd home
ls -l
cd /home/jenkins/workspace/Whentest_master-ZU6DVJQ4JFAPVEHQI5O7A4H5I6PRR6I3XUX3J7XNZOJXCY7K44PA/
ls -l'''
          sh 'touch testfilels123'
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