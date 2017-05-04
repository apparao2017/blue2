pipeline {
  agent any
  stages {
    stage('Stage1') {
      steps {
        git(url: 'https://github.com/apparao2017/mvnrepo', branch: 'master')
      }
    }
    stage('Stage2') {
      steps {
        parallel(
          "Stage2": {
            sh 'mvn clean'
            
          },
          "step2": {
            sh 'mvn compile'
            
          },
          "step3": {
            sh 'mvn package'
            
          }
        )
      }
    }
    stage('Stage3') {
      steps {
        sh 'mvn deploy'
      }
    }
  }
}