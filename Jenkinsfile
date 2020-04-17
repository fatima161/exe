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
                    inventory: '${WORKSPACE}/inventory.ini',
                    colorized: true,
                    playbook: '${WORKSPACE}/playbook.yml',
                )               
            }
        }    
	}
}