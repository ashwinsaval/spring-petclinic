pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './mvnw clean package'
      }
    }
    stage('SonarQube Analysis') {
      steps {
        withSonarQubeEnv(installationName: 'SonarQube-Assignment1') {
          sh "./mvnw verify sonar:sonar"
        }
      }
    }
  }
}