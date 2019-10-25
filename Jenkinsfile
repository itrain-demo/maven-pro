node {
   
   stage('Code Checkout') { // for display purposes
    git credentialsId: 'githubid', url: 'https://github.com/itrainpadman/maven-examples.git'  
   }
   stage('Code Build') {
    withMaven(jdk: 'jdk', maven: 'mavn') {
     sh 'mvn clean compile'
    }  
   }
   stage('Unit Test') {
       withMaven(jdk: 'jdk', maven: 'mavn') {
        sh 'mvn test'
     }  
   }
   stage('SonarQube Analysis') {
       withMaven(jdk: 'jdk', maven: 'mavn') {
       mvn verify sonar:sonar \
  -Dsonar.projectKey=maven-examplle-itraindemo \
  -Dsonar.organization=itraindemo \
  -Dsonar.host.url=https://sonarcloud.io \
  -Dsonar.login=6653f80343799f05f8084f1df17bc79b444158de
       }
   } 
   stage('Archive to Jfrog') {
   } 
   stage('Docker Image') {
   } 
   stage('Deploy to Prods') {
   } 
}
