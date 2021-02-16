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
		
			steps{
			
				echo 'deploying the application...'
			
			}
			
		}

	}

}