node('master') 
{
    	stage('Continuous Download') 
	{
    	git 'https://github.com/chandu2br/DevOpsSample01.git'
	}
	stage('Continuous Build') 
	{
    	sh 'mvn package'
	}
	stage('Continuous Deployment') 
	{
    	sh 'scp  /root/.jenkins/workspace/MultiBranchJob_master/webapp/target/webapp.war   ubuntu@172.31.34.67:/var/lib/tomcat8/webapps/qaenv.war'
	}
	stage('Continuous Testing') 
	{
    	sh 'echo "Tesing Passed"'
	}
	stage('Continuous Delivery') 
	{
    	sh 'scp  /root/.jenkins/workspace/MultiBranchJob_master/webapp/target/webapp.war   ubuntu@172.31.46.13:/var/lib/tomcat8/webapps/prodenv.war'
	}
}

