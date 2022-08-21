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
	//agent any
	//agent{ docker { image 'maven:3.6.3'} }
	agent{ docker { image 'node:13.8'} }
	stages{
		stage('Build'){
			steps{
				sh 'node --version'
				echo "Build"
			}
		}
		stage('Test'){
			steps{
 				echo "Test"
			}
		}
		stage('Integration Test'){
			steps{
 				echo "Integration Test"
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

