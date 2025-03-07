pipeline{
 tools{
        jdk 'JAVA_HOME'
        maven 'M2_HOME'
    }
     agent any
	  
	  stages{
	  
	  stage("checkout"){
	   steps{
	   git 'https://github.com/smrutidevops2025/maven-test.git' 
	   }
	                  }
	
	   stage("compile"){
	    steps{
		 sh 'mvn compile'
		}
		}
       stage("test"){
	    steps{
		 sh 'mvn test'
		}
		}
	
       stage("package"){
	    steps{
		 sh 'mvn clean package'
                 sh "mv target/*.jar target/myweb.jar"

		}
		}
stage(backup)
		  {
  steps{

	nexusArtifactUploader artifacts: [[artifactId: 'app', classifier: '', file: 'target/myweb.jar', type: '1.6']], credentialsId: 'nexus', groupId: 'com.idream', nexusUrl: '54.242.187.158:8081/repository/maven-releases/', nexusVersion: 'nexus3', protocol: 'http', repository: 'maven-releases', version: 'app1'
	  
  }
	
}
	}
	}
