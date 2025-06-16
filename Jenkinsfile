pipeline{
	agent { label 'Jenkins-Agent'}
	tools{
		jdk 'java17'
		maven 'Maven3'	
	}
	stages{
	   stage( "Cleanup Workspace"){
		   steps {
		   cleanWs()	   
		   }
	   }
	   stage("checkout from SCM"){
		   steps{
		      git branch: 'main' , credentialsId: 'github' , url: 'https://github.com/mellogreen/register-app'
	           }
	   }
	   stage("Build Application"){
		   steps {
		      sh "mvn ckean package"   
		   }
	   }
	   stage( "Test Application"){
		   steps {
		      sh "mvn test"	   
		   }
	   }
   }
}
