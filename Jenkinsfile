pipeline {
  agent any
  stages {
    stage('Git clone') {
      steps {
        sh 'git clone https://github.com/spring-projects/spring-petclinic'
      }
    }

    stage('Disp contents') {
      steps {
        sh 'ls'
      }
    }
    
    stage('Build') {
      steps {
        dir('spring-petclinic') {
          sh './mvnw package'
        }
      }
    }

    stage('Ansible') {
      steps {
        sh 'ansible-playbook -i hosts site.yml'
      }
    }

  }
}
