pipeline {

agent any

stages  {

	stage('Build') {
	steps {
			withMaven(maven: 'maven_3_6_1') {
			sh 'mvn clean package'
			
			}
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
