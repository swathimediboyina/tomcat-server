node{
  stage('SCM Checkout'){
    git 'https://github.com/swathimediboyina/tomcat-server.git'
  }
  stage('compile-package'){
    // Get maven home path
    def mvnHome = tool name: 'maven', type: 'maven'
    sh "${mvnHome}/bin/mvn package" 
  }
  //stage('Email Notification'){}
  
  stage('Deploy to Tomcat'){
  
  deploy adapters: [tomcat9(credentialsId: '73f0f8f3-b317-4a0f-8997-e213d656cc70', path: '', url: 'http://3.108.3.83:8081/')], contextPath: 'JenkinsWar1-0.0.1-SNAPSHOT', war: '**/*.war'

  }
}
