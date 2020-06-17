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
			dir('/var/lib/jenkins/') {
    			sh 'git clone --bare /var/lib/jenkins/workspace/test_master/ test_master.git'
              }
	     }
	} 
