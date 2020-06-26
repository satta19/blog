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
    			sh 'git clone --bare /var/lib/jenkins/workspace/MyFirstJob_master/ MyFirstJob.git'
			}
              }
	     }
	} 
}
