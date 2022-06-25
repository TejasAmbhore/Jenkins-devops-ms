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
	agent any
	// agent { docker { image 'maven:3.8.6' } }
	// agent { docker { image 'node:18.4'}}
	stages {
		stage('Build') {
			steps {
				// sh "node --version"
				echo "Build"
				echo "PATH -- $PATH"
				echo "BUILD_NUMBER -- $env.BUILD_NUMBER"
				echo "BUILD ID -- $env.BUILD_ID"
				echo "BUILD TAG -- $env.BUILD_TAG"
				echo "BUILD URL -- $env.BUILD_URL"
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
