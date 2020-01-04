pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sleep 20
        echo 'Success!!!'
        archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true, allowEmptyArchive: true)
        echo 'I am a ${BUZZ_NAME}'
      }
    }
    stage('test') {
      steps {
        echo 'Another message'
        junit(testResults: '**/surefire-reports/**/*.xml', allowEmptyResults: true)
      }
    }
  }
  environment {
    BUZZ_NAME = 'worker bee'
  }
}