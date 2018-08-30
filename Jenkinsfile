pipeline {
  agent any
  stages {
    stage('stage-1') {
      environment {
        TEST1 = 'test4'
      }
      parallel {
        stage('stage-1-1') {
          environment {
            TEST2 = 'test2'
            TEST1 = 'test3'
          }
          steps {
            sh '''echo ${WORKSPACE}

echo ${TEST2}
'''
            sh 'pwd'
            sh(returnStatus: true, script: 'ls -l')
            echo "Hello ${params.PERSON}"
          }
        }
        stage('stage-1-2') {
          steps {
            sh '${PERSON}'
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
'''
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