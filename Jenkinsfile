pipeline {
  agent any
  tools { 
        maven 'Maven_3_8_4'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
				withCredentials([string(credentialsId: 'c84d70437edee4057196e26c24c618a56e6be0f8', variable: 'SONAR_TOKEN')]) {
            sh '''
              mvn clean verify org.sonarsource.scanner.maven:sonar-maven-plugin:5.8.0.7211:sonar \
                -Dsonar.host.url=https://sonarcloud.io \
                -Dsonar.organization=dso_buggy_app \
                -Dsonar.projectKey= dso_buggy_app \
                -Dsonar.token=$SONAR_TOKEN
            '''


				
		/*sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=dso_buggy_app -Dsonar.organization=dso_buggy_app -Dsonar.host.url=https://sonarcloud.io -Dsonar.token=c84d70437edee4057196e26c24c618a56e6be0f8'*/
			}
        } 
  }
}
