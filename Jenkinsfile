pipeline {
  agent {
    node {
      label 'workstation'
    }
   }

parameters {
  choice(name: 'env', choices ['dev','prod'], description: 'Pick your choice of Environment')
  choice(name: 'component',defaultValue:'', description: 'Component Name')
}

stages {
  stage ('Ansible')
    steps {
      sh 'ansible-playbook -i ${component}-${dev}.awsdevopsb01.online, roboshop.yml -e ansible_user=centos -e ansible_password=DevOps321 -e env=${env}'
    }
 }

post {
  always {
    cleanWs()
  }
}

}