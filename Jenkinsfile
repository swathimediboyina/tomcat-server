node{
  stage('SCM Checkout'){
    git 'https://github.com/Ramapuram-Deepa/tomcat-server.git'
  }
  stage('compile-package'){
    // Get maven home path
    def mvnHome = tool name: 'maven-3', type: 'maven'
    sh "${mvnHome}/bin/mvn package" 
  }
  //stage('Email Notification'){}
  
  stage('Deploy to Tomcat'){
  
    sshagent(['fa33aaf1-c0e4-42d6-a339-8f965b6b5164']) {
    sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@172.31.21.110:/home/ec2-user/deepa/tomcat'
}
  }
}
