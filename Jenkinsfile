pipeline {
  agent any
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            sleep 20
            echo 'Success!!!'
            archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true, allowEmptyArchive: true)
            echo 'I am a ${BUZZ_NAME}'
          }
        }
        stage('build new') {
          steps {
            echo 'my new parallel build'
          }
        }
      }
    }
    stage('test') {
      parallel {
        stage('test') {
          steps {
            echo 'Another message'
            junit(testResults: '**/surefire-reports/**/*.xml', allowEmptyResults: true)
          }
        }
        stage('new test') {
          steps {
            echo 'my new test '
          }
        }
      }
    }
  }
  environment {
    BUZZ_NAME = 'worker bee'
  }
}