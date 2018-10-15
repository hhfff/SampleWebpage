pipeline {
  agent none
  stages {
    stage('Build') {
      steps {
        echo 'start build'
      }
    }
    stage('Test') {
      steps {
        echo 'start test'
      }
    }
    stage('Deploy') {
      agent {
        docker {
          image 'nginx'
          args '''-p 8181:80
'''
        }

      }
      steps {
        echo 'start deploy'
        sh '''docker build -t webpage .














docker run -d -p 8000:80 webpage'''
      }
    }
  }
}