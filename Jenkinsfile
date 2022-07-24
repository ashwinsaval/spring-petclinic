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
        def mvn = tool 'Default Maven';
        withSonarQubeEnv() {
          sh "${mvn}/bin/mvn verify sonar:sonar -Dsonar.projectKey=assignment1-sonarqube"
        }
      }
    }
  }
}