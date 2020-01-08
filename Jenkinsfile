pipeline {
  agent none
  stages {
    stage('build') {
      agent {
        node {
          label 'Anjana'
        }

      }
      steps {
        sleep 2
        echo 'Success!!!'
        echo 'I am a ${BUZZ_NAME}'
      }
    }
    stage('test') {
      agent {
        node {
          label 'Anjana'
        }

      }
      steps {
        echo 'Another message'
      }
    }
  }
  environment {
    BUZZ_NAME = 'worker bee'
  }
}