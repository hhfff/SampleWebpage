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
cp -r /statichtml/* /usr/share/nginx/html
cd /usr/share/nginx/html
ls
cat index.html'''
      }
    }
  }
}