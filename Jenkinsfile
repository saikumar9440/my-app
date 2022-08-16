pipeline {
  agent any
  stages {
    stage('Maven Build') {
      steps {
        sh 'mvn clean package'
        sh "the JOB URL is $JOB_UR"
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
