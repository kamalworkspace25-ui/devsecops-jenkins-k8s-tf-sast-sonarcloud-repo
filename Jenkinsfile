pipeline {
  agent any
  tools { 
        maven 'Maven_3_8_4'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar -Dsonar.projectKey=dso_buggy_app -Dsonar.organization=dso_buggy_app -Dsonar.host.url=https://sonarcloud.io -Dsonar.token=c84d70437edee4057196e26c24c618a56e6be0f8'
			}
        } 
  }
}
