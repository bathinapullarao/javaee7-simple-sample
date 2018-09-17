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
  	sh "mvn package"
	sh "mvn deploy"
	sh "mvn release:clean -P release"
	}
}
