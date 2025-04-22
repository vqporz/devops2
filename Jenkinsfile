pipeline {
  agent any
  tools { 
<<<<<<< HEAD
        maven 'Maven_3.2.5'  
=======
        maven 'Maven_3_5_2'  
>>>>>>> 265dcad (adding sac)
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
<<<<<<< HEAD
		      sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=vincetestwebapp -Dsonar.organization=vincetestwebapp -Dsonar.host.url=https://sonarcloud.io -Dsonar.token=50de70d425b3c72720f1b0d497b3bf129248ab16'
			}
        } 
=======
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=asgbuggywebapp -Dsonar.organization=asgbuggywebapp -Dsonar.host.url=https://sonarcloud.io -Dsonar.token=932558e169d66a8f1d1adf470b908a46156f5844'
			}
    }

	stage('RunSCAAnalysisUsingSnyk') {
            steps {		
				withCredentials([string(credentialsId: 'SNYK_TOKEN', variable: 'SNYK_TOKEN')]) {
					sh 'mvn snyk:test -fn'
				}
			}
    }		
>>>>>>> 265dcad (adding sac)
  }
}
