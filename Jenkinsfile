pipeline {
  agent any
  stages {
    stage('stage1') {
      steps {
        sleep 1
      }
    }
    stage('stage2') {
      steps {
        sleep 1
      }
    }
    stage('git') {
      steps {
        git(url: 'https://github.com/lijiaxing10086/dbcourses.git', branch: 'branch1', changelog: true, credentialsId: 'lijiaxing10086')
      }
    }
  }
}