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
        sh '''ls -a
cd statichtml
ls -a
cp * /usr/share/nginx/html

curl http://localhost:80/index.html'''
      }
    }
  }
}