pipeline {
	agent any
		tools {
		maven 'Maven'
		jdk 'jdk'
		}
		stages {
			stage('Checkout') {
				steps {
					git branch: ‘main’, url: 'https://github.com/Shraddhacs2005/mavenapp2'
				}
			}
			stage('Build') {
				steps {
					sh 'mvn clean package'
				}
			}
			stage('Test') {
				steps {
					sh 'mvn test'
				}
			}
			stage('Run Application') {
				steps {
// Start the JAR application
				 	sh 'java -jar target/mavenapp2-1.0-SNAPSHOT.jar'
				}
			}
		}
		post {
			success {
				echo 'Build and deployment successful!'
			}
			failure {
				echo 'Build failed!'
			}
		}
}
