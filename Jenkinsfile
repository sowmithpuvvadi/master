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
                     sh "ansible-playbook all deploy.yml"
  
            }
        }
    }
}
