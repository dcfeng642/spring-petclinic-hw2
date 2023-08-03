pipeline {
  agent any
  stages {
    stage('Git clone') {
      steps {
        sh 'git clone https://github.com/dcfeng642/spring-petclinic.git'
      }
    }
    
    stage('Build') {
      steps {
        sh './spring-petclinic/mvnw package'
      }
    }

    stage('Ansible') {
      steps {
        sh 'ansible-playbook -i hosts spring-petclinic/site.yml'
      }
    }

  }
}
