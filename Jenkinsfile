pipeline {
 agent none
 stages{
  stage("build and SonarQube Analysis")
  {
   agent any
    steps {
	 withSonarQubeEnv('testsonarq')
	 {
	  sh "mvn clean package sonar:sonar -Dsonar.projectKey=sonarqube -Dsonar.projectName='sonarqube'"
	 }
	}
  }
 }
}
