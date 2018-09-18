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
	stage('prepare release')
	{sh "mvn dependency:get -Durl=http://192.168.91.49:8081/nexus/content/repositories/snapshots -Dartifact=com.my.company:common:LATEST-Dtransitive=false -Ddest=. -s settings.xml"
	}
}
