// SCRIPTED Pipeline
// node {
// 	stage('Build') {
// 		echo "Build"
// 	}
// 	stage('Test') {
// 		echo "Test"
// 	}
// 	stage('Integration Test') {
// 	echo "Integration Test"
// 	}
// }
// OR
// node {
// 	echo "Build"
// 	echo "Test"
// 	echo "Integration Test"
// }

//Declarative Pipeline
pipeline {
	agent any
	// agent{ docker { image 'maven:3.6.3'} }
	// agent{ docker { image 'node:13.8'} }
	environment{
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		// stage('Build'){
		stage('Checkout'){
			steps{
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
			}
		}
		stage('Compile'){
			steps{
				sh "mvn clean compile"
			}
		}
		stage('Test'){
			steps{
 			//	echo "Test"
			   sh "mvn test"
			}
		}
		stage('Integration Test'){
			steps{
 				// echo "Integration Test"
				sh "mvn failsafe:integration-test failsafe:verify"
			}
		}
		stage('Package'){
			steps{
				sh "mvn package -DskipTests"
			}
		}
		stage('Build Docker Image'){
			steps{
				//"docker build -t in28min/currency-exchange-devops:${env.BUILD_TAG}"
				script{
					dockerImage = docker.build("sridharkesari/currency-exchange-devops:${env.BUILD_TAG}")
				}
			}
		}
		stage('Push Docker Image'){
			steps{
				script{
					docker.withRegistry('','dockerhub'){
					dockerImage.push();
					dockerImage.push('latest');
					}
				}
			}
		}
	} 
	
	post{
		always{
			echo 'I am awesome. I run always - SridharKesari'
		}
		success{
		echo 'I run when you are successful - SridharKesari'
	    }
	    failure{
		echo 'I run when you fail - SridharKesari'
	    }
	}
}

