pipeline {
    agent any



//	environment {
//		M2_INSTALL = "/home/siddharth/Destros/Maven/apache-maven-3.6.3"
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
				sh "echo "hello world""
				
		}
		}
    }
}
