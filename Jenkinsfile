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
        }

        sh "docker run -d -p 8000:80 my-image:${env.BUILD_ID}"
      }
    }
  }
}