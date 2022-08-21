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
	stages{
		stage('Build'){
			steps{
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
		echo 'I am awesome. I run always - SridharKesari'
	}
	success{
		echo 'I run when you are successful - SridharKesari'
	}
	failure{
		echo 'I run when you fail - SridharKesari'
	}
}

