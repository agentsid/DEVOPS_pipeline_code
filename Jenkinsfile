pipeline {
    agent any



//	environment {
//		M2_INSTALL = "/usr/share/maven/bin"
//	}

    stages {
		stage('Clone-Repo') {
			steps {
				checkout scm
			}
		}
		stage('Build') {
	    	steps {
				sh 'mvn install -DskipTests'
			}
	    }
		stage('Unit Tests') {
			steps {
				sh 'mvn surefire:test'
			}
		}
		stage('Deployment') {
	    	steps {
				sudo cp /root/.jenkins/workspace/pipeline/target/gamutkart.war /root/.jenkins/workspace/pipeline/apache-tomcat-8.5.38/webapps/'
				
         	}
		}
    }
}
