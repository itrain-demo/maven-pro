node {
   
   stage('Code Checkout') { // for display purposes
    git credentialsId: 'githubid', url: 'https://github.com/itrainpadman/maven-examples.git'  
   }
   stage('Code Build') {
    withMaven(jdk: 'JDK-1.8', maven: 'Maven3.6.1') {
     sh 'mvn clean compile'
    }  
   }
   stage('Unit Test') {
       withMaven(jdk: 'JDK-1.8', maven: 'Maven3.6.1') {
        sh 'mvn test'
     }  
   }
   stage('SonarQube Analysis') {
       
   } 
   stage('Archive to Jfrog') {
   } 
   stage('Docker Image') {
   } 
   stage('Deploy to Prods') {
   } 
}
