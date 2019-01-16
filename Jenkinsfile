pipeline 
{
    agent 
	{
        node 
		{
            label 'DBB102'
            //customWorkspace "/u/jenkins/workspace/temp/billsTest1"
        }
    }
    environment 
	{
        //CI = 'true'
	//WS = '/u/CMN/jenkins/'
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
