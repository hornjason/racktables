pipeline { 
  agent { 
    node { 
      label 'docker'
    }
  }
 
  stages {
    stage ('Checkout Code') {
      steps {
        checkout scm
      }
    }
    stage ('Verify Tools'){
      steps {
          docker: { sh "docker -v" }
      }
    }

    stage ('Build container') {
      steps {
        sh "docker build -t jasonhorn/node-example:latest ."
        sh "docker tag jasonhorn/node-example:latest badamsbb/node-example:v${env.BUILD_ID}"
      }
    }
}
