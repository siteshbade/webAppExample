pipeline {
    agent any
	tools {
		maven 'MAVEN_HOME'
		
	}

    stages {
        stage ('Compile Stage') {

            steps {
                
                    bat 'mvn clean compile'
                
            }
        }

        stage ('Testing Stage') {

            steps {
                
                    bat 'mvn test'
                }
            }
        


        stage ('Deployment Stage') {
            steps {
                
                    deploy adapters: [tomcat8(credentialsId: 'Tomcate', path: '', url: 'http://localhost:8082/')], contextPath: 'sample-java-app', war: '**/*.war'
                }
            }
        }
    }
