pipeline {
  agent any
  
  stages {
    stage('Maven Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage('Deploy to Tomcat') {
      steps {
        sshagent(['tomcat-dev']) {
          //copy warfile to tomcat server
            sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@172.31.81.193:/opt/tomcat8/webapps/app.war'
          //stop tomcat server
            sh "ssh ec2-user@172.31.81.193 /opt/tomcat8/bin/shutdown.sh"
          //start tomcat server
            sh "ssh ec2-user@172.31.81.193 /opt/tomcat8/bin/startup.sh"
        }
      }
    }
  }
  post {
    success {
      archiveArtifacts artifacts: 'target/*.war'
      cleanWs()
    }
  }
}
