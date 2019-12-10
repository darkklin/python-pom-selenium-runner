pipeline{
	agent any
	stages{
		stage("Pull latest Image"){
			steps{
				sh "docker pull darkklin/python-pom-selenium"
			}
		}
		stage("Run The Test"){
			steps{
				sh "docker-compose up test-module"
		   }
		}
		stage("reports"){
			steps {
			script {
            allure([
                    includeProperties: false,
                    jdk: '11.0.4"',
                    properties: [],
                    reportBuildPolicy: 'ALWAYS',
                    results: [[path: '/home/qa/jenkins/workspace/python-pom-selenium-runner']]
            ])
    }
    }
		}
	}
	
}