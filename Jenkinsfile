pipeline {
    agent any
//       tools {
//          maven 'maven'
//        }
    stages {
        stage ('Clone') {
            steps {
                git branch: 'master', url: "https://github.com/midhunthampi/WebApp.git"
            }
		 post {
                 success {
		     slackSend (color: '#FFFF00', message: "Clone Successful: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")
                 }
	         failure {
		     slackSend (color: '#FFFF00', message: "Clone Failed: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")
                 }   
             }
        }
        
        stage('Sonarqube') {   
		       steps {
//                             withSonarQubeEnv(credentialsId: 'sonarqube1', installationName: 'sonarqube1') {    sh 'mvn clean package sonar:sonar -Dsonar.host.url=http://sonar-devops.westus.cloudapp.azure.com -Dsonar.login=admin -Dsonar.password=admin -Dsonar.sources=. -Dsonar.tests=. -Dsonar.test.inclusions=**/test/java/servlet/createpage_junit.java -Dsonar.exclusions=**/test/java/servlet/createpage_junit.java'
//          }
			       echo "Sonar Qube Code Review Completed"
         }		
	}
	    
   
	
    }
}
