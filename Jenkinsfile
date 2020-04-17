pipeline {
	agent {
		docker {
			image 'node:6-alpine'
		}
	}
	stages {
		stage('Build') {
			steps {
				sh 'npm install'
			}
		}
        stage('Test') {
			steps {
				sh 'npm test'
			}
		}
        stage('Deploiement Ansible') {
            steps{
                ansiblePlaybook (
                    inventory: 10.189.100.192,
                    colorized: true,
                    playbook: 'playbook.yml'
                )
                ansibleVault (
                    vaultCredentialsId: 

                )

            }
        }    
	}
}