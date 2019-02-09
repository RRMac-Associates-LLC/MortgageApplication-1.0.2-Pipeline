pipeline 
{
	agent 
	{
		node 
		{
			label 'DBB102'
			customWorkspace "/u/CMN/jenkins/pipelines/BillsTest1/MultiBranchPipeline2"
		}
	}
	environment 
	{
		//CI = 'true'
		WS = '/u/CMN/jenkins/pipelines/BillsTest1/MultiBranchPipeline2'
		CC = 'clang'
	}
	stages 
	{
		stage('Checkout') 
		{ // for display purposes
			steps 
			{
				checkout scm 		
			}
		}
		stage('Build') 
		{
			steps 
			{
				ws("${env.WS}")
				{
					withEnv(["DIR=${env.WS}/MortgageApplication-1.0.2/MortgageApplication/build/build.groovy",
				            	'JAVA_HOME=/usr/lpp/java/J8.0_64',
				            	'IBM_JAVA_ENABLE_ASCII_FILETAG=ON',
							'CMNSYS=P',
							'WAIT_FOR_JOB=180',
							'ENV=PROD',
							'_BPXK_AUTOCVT=ON', 
							'ALVL=PROD',
							'DLVL=PROD',
							'FLVL=PROD',
							'PIPELINE=Y'])
					{
						echo 'build.............................................................................................'   
						//sh encoding: 'IBM1047', script: 'env'
						//sh '/bin/sh /u/jenkins/scripts/convertToIBM1047.sh'						
						sh '/bin/sh /u/jenkins/workspace/temp/runGroovyz.sh'
						//sh '/bin/sh /u/jenkins/scripts/convertToISO8859.sh'
					}
				}
			}
		}
		stage('Test') 
		{
			steps 
			{
				echo 'Test...............................................................................................'
			}
        }
		stage('Results') 
		{
			steps 
			{			    
				//junit '**/target/surefire-reports/TEST-*.xml'
				//archive 'target/*.jar'
				echo 'Pipeline complete'
			}
		}
    }
}
