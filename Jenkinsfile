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
      agent any
      steps {
        script {
          image=docker.build("my-image:${env.BUILD_ID}")
          image.run('-p 8000:80') {}
        }

      }
    }
  }
}