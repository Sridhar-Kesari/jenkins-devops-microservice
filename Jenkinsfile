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
Pipeline {
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
}

