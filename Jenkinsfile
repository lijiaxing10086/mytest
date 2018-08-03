pipeline {
  agent any
  stages {
    stage('stage1') {
      steps {
        sh 'mkdir branch1'
        sh 'mkdir branch2'
      }
    }
    stage('stage2') {
      parallel {
        stage('stage2') {
          steps {
            ws(dir: 'branch1') {
              sh 'pwd'
              git(url: 'https://github.com/lijiaxing10086/dbcourses.git', branch: 'lijiaxing')
              sh 'ls'
            }
            
            sh 'ls -l'
          }
        }
        stage('') {
          steps {
            ws(dir: 'branch2') {
              git(url: 'https://github.com/lijiaxing10086/mytest.git', branch: 'master')
              sh 'ls'
            }
            
          }
        }
      }
    }
  }
}