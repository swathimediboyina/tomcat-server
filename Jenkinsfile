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
  
  deploy adapters: [tomcat9(credentialsId: 'fa33aaf1-c0e4-42d6-a339-8f965b6b5164', path: '', url: 'http://52.66.225.247:8081/')], contextPath: 'JenkinsWar1-0.0.1-SNAPSHOT', war: '**/*.war'

  }
}
