pipeline {
  agent any
  stages {
    stage('dir') {
      steps {
        sh '''mkdir test
touch testfile'''
        sleep 60
      }
    }
    stage('ls -1') {
      steps {
        sh 'ls -l'
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '84a80b45-4deb-4847-ac7b-44afdae9c313', url: 'http://192.168.1.52/Bonobo.Git.Server/Mytest.git']]])
        sh '''ls -l
pwd
sleep 60'''
        checkout([$class: 'SubversionSCM', additionalCredentials: [], excludedCommitMessages: '', excludedRegions: '', excludedRevprop: '', excludedUsers: '', filterChangelog: false, ignoreDirPropChanges: false, includedRegions: '', locations: [[cancelProcessOnExternalsFail: true, credentialsId: '84a80b45-4deb-4847-ac7b-44afdae9c313', depthOption: 'infinity', ignoreExternalsOption: true, local: '.', remote: 'https://192.168.1.52/svn/Test']], quietOperation: true, workspaceUpdater: [$class: 'UpdateUpdater']])
        sh '''ls -l
pwd
sleep 60'''
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