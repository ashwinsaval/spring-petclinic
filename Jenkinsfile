pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './mvnw clean verify'
      }
    }
    stage('Deploy') {
      steps {
        sh '''
          ansible --version
          ansible-playbook --version
          ansible-galaxy --version
        '''
        sh 'ansible-playbook -i inventory/petclinic.hosts playbooks/petclinic.yml'
      }
    }
  }
}