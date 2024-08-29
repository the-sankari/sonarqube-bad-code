pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  stages {
    stage('Scan') {
      steps {
        nodejs (nodeJSInstallationName: 'node') {
        withSonarQubeEnv(installationName: 'sonarqube') { 
           sh "npm install sonar-scanner"
           sh "npm run sonarqube"
        }
       }
      }
    }
  }
}
