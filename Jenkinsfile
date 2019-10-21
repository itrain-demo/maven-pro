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
       withMaven(jdk: 'JDK-1.8', maven: 'Maven3.6.1') {
       sh 'mvn sonar:sonar \
           -Dsonar.projectKey=maven-example-padman \
           -Dsonar.organization=itrainpadman \
           -Dsonar.host.url=https://sonarcloud.io \
           -Dsonar.login=ef4b147fcb4eea67d0e0a5a182f4b85289f2c8c1'
       }
   } 
   stage('Archive to Jfrog') {
   } 
   stage('Docker Image') {
   } 
   stage('Deploy to Prods') {
   } 
}
