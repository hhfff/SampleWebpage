pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'start build'
        sh '''git clone https://github.com/hhfff/SampleWebpage
ls '''
      }
    }
    stage('Test') {
      steps {
        echo 'start test'
      }
    }
    stage('Deploy') {
      steps {
        echo 'start deploy'
      }
    }
  }
}