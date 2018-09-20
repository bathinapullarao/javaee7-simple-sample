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
	stage('Build clean package')
	{
  	sh "mvn clean package deploy"
	}
	stage('clean release')
	{
	sh "mvn release:clean -P release"
	}
}
