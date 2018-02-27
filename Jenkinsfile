pipeline {
  agent any
  stages {
    stage('Stage 1') {
      parallel {
        stage('Stage 1') {
          agent {
            node {
              label 'master'
            }
            
          }
          steps {
            echo 'Print Message'
          }
        }
        stage('Stage 2') {
          agent {
            node {
              label 'slave1'
            }
            
          }
          steps {
            archiveArtifacts '**/target/*'
            junit '**/target/surefire-reports/TEST-*.xml'
          }
        }
      }
    }
  }
}