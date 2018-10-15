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
          docker.build("my-image:${env.BUILD_ID}")
          docker.image("my-image:${env.BUILD_ID}").withRun('-p 8000:80') {}
        }

      }
    }
  }
  post {
    success {
      script {
        docker.image("my-image:${env.BUILD_ID}").withRun('-p 8000:80') {}
      }


    }

  }
}