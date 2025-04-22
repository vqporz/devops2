pipeline {
  agent any
  tools { 
        maven 'Maven_3.2.5'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
		      sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=vincetestwebapp -Dsonar.organization=vincetestwebapp -Dsonar.host.url=https://sonarcloud.io -Dsonar.token=50de70d425b3c72720f1b0d497b3bf129248ab16'
			}
    }
	stage('RunSCAAnalysisUsingSnyk') {
            steps {		
				withCredentials([string(credentialsId: 'SNYK_TOKEN', variable: 'SNYK_TOKEN')]) {
					sh 'mvn snyk:test -fn'
				}
			}
    }		
  }
}
