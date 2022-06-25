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

	environment {
		dockerHome = tool "myDocker"
		mavenHome = tool "myMaven"
		PATH =  "$dockerHome/bin:$mavenHome/bin:$PATH"
	}

	agent any
	// agent { docker { image 'maven:3.8.6' } }
	// agent { docker { image 'node:18.4'}}
	stages {
		stage('Checkout') {
			steps {
				sh "mvn --version"
				sh "docker version"
				echo "Build"
				echo "PATH -- $PATH"
				echo "BUILD_NUMBER -- $env.BUILD_NUMBER"
				echo "BUILD ID -- $env.BUILD_ID"
				echo "BUILD TAG -- $env.BUILD_TAG"
				echo "BUILD URL -- $env.BUILD_URL"
			}
		}

		stage('Compile') {
			steps {
				sh "mvn clean compile"
			}
		}

		stage('Test') {
			steps {
				sh "mvn test"
			}
		}

		stage('Integration Test') {
			steps {
				echo "mvn failsafe:integration-test failsafe:verify"
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
