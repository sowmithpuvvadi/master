pipeline {
    agent any
     
    stages {
      stage('checkout') {
           steps {
             
                git branch: 'main', url: 'https://github.com/sowmithpuvvadi/master.git'
             
          }
        }
         
        stage('Ansible Deploy') {
             
            steps {
                     sh "ansible-playbook -i hosts deploy.yml"
  
            }
        }
    }
}
