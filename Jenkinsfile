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
		stage('Ansible Init') {
            steps {
                script {
                
               def tfHome = tool name: 'Ansible'
                env.PATH = "${tfHome}:${env.PATH}"
                 sh 'ansible --version'
                    
            }
            }
        }
	} 
	
	post {
        always {
            echo 'One way or another, I have finished'
	    dir('/var/lib/jenkins/archive') {
            deleteDir() /* clean up our workspace */
	    }
	}
        }
}
