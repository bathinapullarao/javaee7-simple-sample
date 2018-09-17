node 
{
	stage('declareEnvVariables')
	{
        def mavenHome  = tool 'myMaven'
        env.PATH = "${mavenHome}/bin:${env.PATH}"
        }
	stage('gitCheckout') 
	{
	checkout scm
    	}
	stage('Build')
	{
  	sh "mvn clean package deploy"
	}
}
