pipeline {
  agent any
  stages {
    stage('Git clone spring-petclinic') {
      steps {
        sh 'git clone https://github.com/spring-projects/spring-petclinic'
      }
    }

    stage('Build app') {
      steps {
        dir('spring-petclinic') {
          sh './mvnw package'
        }
      }
    }

    stage('Ansible for scp and run server') {
      steps {
        sh 'ansible-playbook -i hosts site.yml'
      }
    }

   stage('Reset build env') {
      steps {
        dir('spring-petclinic') {
          deleteDir()
        }
      }
    }
    
  }
}
