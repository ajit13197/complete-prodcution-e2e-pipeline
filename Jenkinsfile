pipeline{
    agent{
       label "jenkins-agent"
    }
    
    tools{

      jdk 'Java17'
      maven 'Maven3'
     }

     stages{
       stage("cleaning workspace"){
         steps {
	    cleanWs()

	 }
       }
      
        stage("checkout from SCM"){
	  steps {
	     git branch: 'main', credentialsId: 'github', url: 'https://github.com/ajit13197/complete-prodcution-e2e-pipeline.git'
	  }

	}
   
        stage("Building the application"){
	  steps{
	    sh "mvn clean install"
	  }

	stage("testing the application"){
	  steps {
	    sh "mvn test"

	  }

	}
	

   }
