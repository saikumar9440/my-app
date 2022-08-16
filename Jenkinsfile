pipeline {
  agent any
  stages {
    stage('Maven Build') {
      steps {
        sh 'mvn clean package'
        echo 'this is jenkkins file demo '
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
