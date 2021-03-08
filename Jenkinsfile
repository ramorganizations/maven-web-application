// Powered by Infostretch 

timestamps {

node () {

	stage ('walmart_project - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/development']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'c7023370-b546-41c8-9a02-f72f784312e4', url: 'https://github.com/ramorganizations/maven-web-application.git']]]) 
	}
	stage ('walmart_project - Build') {
 	
// Unable to convert a build step referring to "hudson.plugins.timestamper.TimestamperBuildWrapper". Please verify and convert manually if required.		// Maven build step
	withMaven(maven: 'maven3.6.3') { 
 			if(isUnix()) {
 				sh "mvn clean package sonar:sonar deploy " 
			} else { 
 				bat "mvn clean package sonar:sonar deploy " 
			} 
 		} 
	}
}
}