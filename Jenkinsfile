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
					inventory: './inventories', 
					playbook: './demo.yaml'
					
				)
            }
        }
                  
 }

}
