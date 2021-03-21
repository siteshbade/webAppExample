pipeline {
 agent any
 def mvnHome = tool 'MAVEN_HOME'
	stages
	{
	stage('checkout SCM')
	{
	 steps{
	 
		checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/siteshbade/webAppExample.git']]])
	      }
	}
	stage('Building application')
	{
	 steps{
			bat "${mvnHome} -Dmaven.test.failure.ignore.clean.package"
			
			
		 }
	
	}
	}
}