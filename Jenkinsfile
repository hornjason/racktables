pipeline {
  agent {
    node {
      label 'docker'
    }
    
  }
  stages {
    stage('Initialize') {
      steps {
        sh '''cat /entrypoint.sh
ps -ef|grep nginx
netstat -tulnp
curl http://localhost/?module=installer&step=5'''
      }
    }
  }
}