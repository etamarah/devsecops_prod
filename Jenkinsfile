pipeline {
  agent any
  tools { 
        maven 'Maven_3_2_5'  
    }
   stages{
    stage ('run maven') {
      steps {
            sh 'mvn clean package -Dmaven.test.skip=true'     
      }
    }
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn -Dmaven.test.failure.ignore verify sonar:sonar -Dsonar.projectKey=tamie -Dsonar.organization=tamie -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=99176cf1baf9dc68b833361f0dd72c4cbb07c2a7'
			}
        } 
  }
}
