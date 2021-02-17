pipeline {

agent any

environment{
	RELEASE='20.04'
}

stages {

	stage("build"){
	
			environment {
				LOG_LEVEL='INFO'
			}

			steps{
			
				echo "building the application ${RELEASE} with log level ${LOG_LEVEL}"
			
			}

		}
		
		stage("test"){
		
			steps{
			
				echo "Testing release ${RELEASE}"
				writeFile file: 'test-results.txt', text: 'passed'
			}
		
		}
		
		stage('deploy'){
		input{
			message 'Deploy?'
			ok 'Do it!'
			parameters{
				string(name: 'TARGET_ENVIRONMENT', defaultValue: 'PROD', description: 'Target deployment envioronment')
			}
		}
		
			steps{
			
				echo "Deploying release ${RELEASE} to environment ${TARGET_ENVIRONMENT}"
			
			}
			
		}

	}
	post{
		success{
			archiveArtifacts 'test-results.txt'
		}
	}

}