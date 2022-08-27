pipeline{
	agent any
	
	stages{
		stage("DOCKER BUILD"){
			steps{
				echo "BUILD stage"
				sh ''' 
					cd /var/lib/jenkins/workspace/final
					docker build -t sandeshhm/jenkins:1.10 .
				'''
			}
		}
		stage("DOCKER PUSH"){
	                 steps{
				sh 'docker image ls'
				sh 'docker push sandeshhm/jenkins:1.10'
				echo "Docker image pushed to docker hub successfuly"
			}
		}
		
		stage("Docker-run"){
			steps{
				echo "Running container"
				sh 'docker run -it -d -p 8060:8080 --name sandeshhm-tomcat sandeshhm/jenkins:1.10'
				
			}
		}
	}
}
