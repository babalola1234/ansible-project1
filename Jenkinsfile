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
					playbook: './demo.yaml')
            }
        }
                  
    post {
        always {
            // Archive the Ansible playbook execution logs
            archiveArtifacts '*.log'
        }
        
        success {
            // Notify success
            echo 'Ansible playbook executed successfully!'
        }
        
        failure {
            // Notify failure
            echo 'Ansible playbook execution failed!'
        }
    }
}
