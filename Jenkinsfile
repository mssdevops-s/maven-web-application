node{
    
def mavenhome = tool name: "maven3.8.4"

properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), [$class: 'RebuildSettings', autoRebuild: false, rebuildDisabled: false], [$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('* * * * *')])])
   
   stage('checkout code'){
    git branch: 'development', credentialsId: 'b6ca9e64-78bf-42e0-a2e0-db8a1e4ee37f', url: 'https://github.com/mssdevops-s/maven-web-application.git'
	}
    stage('build'){
	sh "${mavenhome}/bin/mvn clean package"
	}
	
/*	
	stage('execute sonarqube report'){
	sh "${mavenhome}/bin/mvn sonar:sonar"
	}
	stage('upload artifacts into nexus'){
	sh "${mavenhome}/bin/mvn deploy"
	}
	
	stage('deploy application into tomcat server'){  
    sshagent(['086e6780-4a9c-4f85-a959-fc5c4fe30412']){ 
    sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@13.235.83.119:/opt/apache-tomcat-9.0.55/webapps/"
   }
	}
   stage('sendemailnotification'){
	  emailext body: '''Build over..
    Regards,
    Swapna M,
    9177602546.''', subject: 'Build over', to: 'rgreddycrp@gmail.com'
    }
*/	  
 } 
 
