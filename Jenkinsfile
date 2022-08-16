pipeline {
  agent any
  stages {
    stage('Maven Build') {
      steps {
        sh 'mvn clean package'
        sh "echo The JOB URL is $JOB_URL"
      }
    }
  }
  post {
    success {
      echo 'this is sucess block'
    }
    failure {
      echo 'this is failure block'
    }
   }
}
