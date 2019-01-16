pipeline 
{
    agent 
    {
        node 
	{
            label 'DBB102'
            customWorkspace "/u/CMN/jenkins/pipelines/MultiBranchPipeline2"
        }
    }
    environment 
    {
        //CI = 'true'
	//WS = '/u/CMN/jenkins/pipelines/MultiBranchPipeline2'
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
                echo 'build.............................................................................................'   
		//sh encoding: 'IBM1047', script: 'env'
		sh '/bin/sh /u/jenkins/workspace/temp/runGroovyz.sh'
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
