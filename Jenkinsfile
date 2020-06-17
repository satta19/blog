pipeline {
	agent any
  
	stages {
		stage ('Prepare') {
		steps {
			echo '\n'
			echo '****GIT PULL***'
			checkout scm
		      }
		}
		stage ('Create bare repo') {
			steps {
			echo '\n'	
			dir('/var/lib/jenkins/archive') {
    			sh 'git clone --bare /var/lib/jenkins/workspace/test_master/ test_master.git'
			}
              }
	     }
		stage ('Copy the bare repo to other server') {
			steps {
				script {
				def remote = [:]
					  remote.host = '172.31.33.204'
					  remote.user = 'root'
					  remote.allowAnyHosts = true
				echo '\n'
			        sshPut remote: remote, from: '/var/lib/jenkins/archive/workspace/test_test_master.git', into: '/opt'
						
					}
				}
			}
		
	} 
}
