pipeline {
agent any
	tools{
	maven 'Maven_3.6.1'
	}
	
stages  {
	stage('Build') {
	steps {
			
			sh 'mvn clean package'
			
			}
			}
			
			
	stage('Deploy') {
	steps {
	          withCredentials([[$class	: 'UsernamePasswordMultiBinding',
	          					credentailsId	: 'PCF_LOGIN',
	          					usernameVariable : 'USERNAME',
	          					passwordVariable : 'PASSWORD']]) {
	          					
	          			sh '/C:/Program Files/Cloud Foundry/cf login -a http://api.run.pivotal.io -u $USERNAME -p PASSWORD'
	          			sh '/C:/Program Files/Cloud Foundry/cf push'
	          			}
	          	}
	          	
	        }
	        
	        }
}
