node 
{
stage('gitCheckout') 
	{
	def mavenHome  = tool 'myMaven'
        env.PATH = "${dockerHome}/bin:${mavenHome}/bin:${env.PATH}"
        checkout scm
    	}
stage('Build')
	{
  sh "mvn package"
	sh "mvn deploy"
	sh "mvn release:clean -P release"
	}
}
