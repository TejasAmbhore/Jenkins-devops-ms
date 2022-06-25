// node {
// 	stage('Build') {
// 		echo "Build"
// 	}
// 	stage('Test') {
// 		echo "Test"
// 	}
// 	stage('Integration Test') {
// 		echo "Integration Test"
// 	}
// }

pipeline {
	// agent any
	// agent { docker { image 'maven:3.8.6' } }
	agent { docker { image 'node:18.4'}}
	stages {
		stage('Build') {
			steps {
				sh "node --version"
				echo "Build"
			}
		}
		stage('Test') {
			steps {
				echo "Test"
			}
		}
		stage('Integration Test') {
			steps {
				echo "Integration Test"
			}
		}
	} 
	post {
		always {
			echo 'Its running'
		}
		success {
			echo 'Successfully running'
		}
		failure {
			echo 'running Failure'
		}
		// changed
		// unstable
	}
}
