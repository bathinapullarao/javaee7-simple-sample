node 
{
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
