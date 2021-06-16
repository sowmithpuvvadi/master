pipeline {
    agent any
     
    stages {
      stage('checkout') {
           steps {
             
                git branch: 'main', url: 'https://github.com/sowmithpuvvadi/master.git'
             
          }
        }
     
          stage('Ansible Init') {
            steps {
                script {
                
               def tfHome = tool name: 'Ansible'
                env.PATH = "${tfHome}:${env.PATH}"
                 sh 'ansible --version'
                    
            }
            }
        }
         
        stage('Ansible Deploy') {
             
            steps {
                     ansiblePlaybook disableHostKeyChecking: true, installation: 'Ansible', inventory: 'hosts', playbook: 'deploy.yml'
  
            }
        }
    }
}
