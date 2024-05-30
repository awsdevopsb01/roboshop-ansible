pipeline {
  agent {
    node {
      label 'workstation'
    }
   }

   options {
     ansiColor('xterm')
   }

parameters {
  choice(name: 'env', choices: ['dev','prod'], description: 'Pick your choice of Environment')
  string(name: 'component', defaultValue:'', description: 'Component Name')
}

stages {
  stage ('Ansible') {
      steps {
        sh 'ansible-playbook -i ${component}-${dev}.nldevopsb01.online, roboshop.yml -e ansible_user=centos -e ansible_password=DevOps321 -e env=${env} -e role_name=${component}'
      }
  }
 }

post {
  always {
    cleanWs()
  }
}
}