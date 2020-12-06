pipeline {
    agent any

	tools {
		maven 'maven3.6'
	}
//
//	environment {
//		M2_INSTALL = "/home/siddharth/Destros/Maven/apache-maven-3.6.3/bin"
//	}

    stages {
		stage('Clone-Repo') {
			steps {
				checkout scm
			}
		}
	
		stage('Build') {
			steps {
				sh 'mvn install -Dmaven.test.skip=true'
			}
		}
		
		stage('Unit Tests') {
			steps {
				sh 'mvn compiler:testCompile'
				sh 'mvn surefire:test'
			}
		}

	
		stage('Deployment') {
			steps {
				sh 'sshpass -p "admin" scp target/gamutgurus.war admin@172.17.0.4:/home/admin/'
				
	    	}
		}
    }
}
