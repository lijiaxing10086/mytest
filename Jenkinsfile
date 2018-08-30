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
        checkout([$class: 'SubversionSCM', additionalCredentials: [], excludedCommitMessages: '', excludedRegions: '', excludedRevprop: '', excludedUsers: '', filterChangelog: false, ignoreDirPropChanges: false, includedRegions: '', locations: [[cancelProcessOnExternalsFail: true, credentialsId: '84a80b45-4deb-4847-ac7b-44afdae9c313', depthOption: 'infinity', ignoreExternalsOption: true, local: '.', remote: 'https://192.168.1.52/svn/Test']], quietOperation: true, workspaceUpdater: [$class: 'UpdateUpdater']])
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
        ws(dir: '/test') {
          sh '''pwd
ls -l
cd ..
ls -l
echo "${WORKSPACE}"'''
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