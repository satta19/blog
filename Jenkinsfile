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
				echo '\n'
			        dir('/var/lib/jenkins/archive') {
				  sh 'sudo su - -c 'scp -r /var/lib/jenkins/archive/test_master.git/ root@172.31.33.204:/opt/''
	}
			}
		}
	} 
}
