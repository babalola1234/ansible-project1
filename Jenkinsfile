pipeline {
    agent {
        label 'slave'
    }
    stages {
        stage('get the code from github') {
            steps {
				// Checkout your source code repository from SCM
                checkout scm
            }
        }
        
        stage('checkout code and run ansible playbook ') {
            steps {
                // Install required packages and dependencies
                ansiblePlaybook(
					credentialsId: 'ansible-ssh', 
					inventory: '/root/ansible-project1/inventory', 
					playbook: '/root/ansible-project1/demo.yaml'
					
				)
            }
        }
                  
 }

}
