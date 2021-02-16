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
			
				echo 'testing the application....'
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
		always{
			echo "Prints whether deploy happened or not."
		}
	}

}