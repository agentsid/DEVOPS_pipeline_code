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
				sh 'sshpass -p "gamut" scp target/gamutkart.war gamut@172.17.0.3:/home/gamut/tomcat/apache-tomcat-8.5.38/webapps'
			        sh 'sshpass -p "gamut" ssh gamut@172.17.0.3 "JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64/" "/home/gamut/tomcat/apache-tomcat-8.5.38/bin/startup.sh"'
				
		}
		}
    }
}
