pipeline {
	agent any
	
	stages{
		stage('Git'){
			echo "clone repo"
			checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'git-cred', url: 'https://github.com/jacksontechtraining/dec6jenkinsfile']]])
		}
		stage('Compile'){
			echo "compiling the script"
			bat 'mvn compile'
		}
		stage('Package'){
			echo "compiling the project"
			bat 'mvn package'
		}
		stage('Dependency'){
			echo "installing project dependency"
			bat 'mvn install'
		}
		stage('Test'){
			echo "testing the project"
			bat 'mvn test'
		}
	}
}