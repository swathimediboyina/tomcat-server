node{
  stage('SCM Checkout'){
    git 'https://github.com/BairaboinaVyshnavi/Tomcatserver.git'
  }
  stage('compile-package'){
    // Get maven home path
    def mvnHome = tool name: 'maven-3', type: 'maven'
    sh "${mvnHome}/bin/mvn package" 
  }
  //stage('Email Notification'){}
  
  stage('Deploy to Tomcat'){
  
    sshagent(['tomcat-dev']) {
    sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@172.31.6.50:/opt/apache-tomcat-10.1.11/webapps'
}
  }
}
