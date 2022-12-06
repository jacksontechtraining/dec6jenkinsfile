pipeline {
	agent any
	
	stages{
		stage('Git'){
			steps{
				echo "clone repo"
				checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'git-cred', url: 'https://github.com/jacksontechtraining/dec6jenkinsfile']]])
			}
		}
		stage('Compile'){
			steps{
				echo "compiling the script"
				bat 'mvn compile'
			}
		}
		stage('Package'){
			steps{
				echo "compiling the project"
				bat 'mvn package'
			}
		}
		stage('Dependency'){
			steps{
				echo "installing project dependency"
				bat 'mvn install'
			}
		}
		stage('Test'){
			steps{
				echo "testing the project"
				bat 'mvn test'
			}
		}
	}
}