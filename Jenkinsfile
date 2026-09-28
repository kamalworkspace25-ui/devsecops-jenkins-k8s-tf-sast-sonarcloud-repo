pipeline {
  agent any
  tools {
    maven 'Maven_3_8_4'
  }
  stages {
    stage('CompileandRunSonarAnalysis') {
      steps {
        withCredentials([string(credentialsId: 'sonarcloud-token', variable: 'SONAR_TOKEN')]) {
          sh '''
            mvn clean verify org.sonarsource.scanner.maven:sonar-maven-plugin:5.8.0.7211:sonar -Dsonar.host.url=https://sonarcloud.io -Dsonar.organization=dsobuggyapp -Dsonar.projectKey=dsobuggyapp -Dsonar.token=$SONAR_TOKEN
          '''
        }
      }
    }
  }
}
