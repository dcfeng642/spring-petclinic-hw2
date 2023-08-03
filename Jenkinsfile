pipeline {
  agent any
  stages {
    stage('Git clone') {
      steps {
        sh 'git clone https://github.com/dcfeng642/spring-petclinic.git'
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
        dir('spring-petclinic') {
          sh 'ansible-playbook -i hosts site.yml'
        }
      }
    }

  }
}
