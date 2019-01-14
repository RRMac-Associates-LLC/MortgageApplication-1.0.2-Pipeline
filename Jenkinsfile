pipeline 
{
	options 
	{
        timeout(time: 3 , unit: 'MINUTES')
    } // options
    agent 
	{
        node 
		{
            label 'BillsPipelineTest'
            //customWorkspace "/u/jenkins/workspace/temp/billsTest1"
        }
    }
	environment
    {
        WS = '/u/CMN/jenkins/pipelines/BillsTest1'
        
		//output_package = null
	} // environment
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
			    ///${env.BUILD_ID}
				ws("${env.WS}")
                {
				   withEnv(["DIR=${env.WS}/MortgageApplication-1.0.2",
				            'JAVA_HOME=/usr/lpp/java/J8.0_64',
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
        				
        			    sh '/bin/sh /u/jenkins/workspace/temp/runGroovyz.sh'
					}
                }
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
