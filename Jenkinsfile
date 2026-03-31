pipeline {
	agent any
	tools {
		maven 'maven'
	}
	stages {
		stage('Checkout') {
			steps {
				git branch: main, url: 'https://github.com/hemanth3007/mvn-practice.git'
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
				sh 'java -jar target/mvnPractice-1.0.jar'
			}
		}
		
	}
	post {
		success {
			echo 'Build and deployment successful'
		}
		failure {
			echo 'Build Failed'
		}
	}
}
