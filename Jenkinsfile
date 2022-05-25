node
{
def mavenHome = tool name: "maven 3.8.5"

properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * *')])])

stage('CheckoutCode')
{
git branch: 'development', credentialsId: 'bec47272-821c-4f9b-9446-95f3261229ab', url: 'https://github.com/anji0128/maven-web-application.git'
}
}

stage('Build')
{
sh "${mavenHome}/bin/mvn clean package"
}
}
/*
stage('ExecuteSonarQubeReport')
{
sh "${mavenHome}/bin/mvn sonar:sonar"
}

stage('UploadArtifactintoNexus')
{
sh "${mavenHome}/bin/mvn deploy"
}

stage('DeployAppIntoTomcatServer')
{
sshagent(['3d9319b6-983d-436e-b5a9-e6a188a0b7fe'])
{
sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@13.126.122.173:/opt/apache-tomcat-9.0.62/webapps"
}
}

stage('SendEmailNotification')
{
emailext body: '''Build is over

Regards,
AJ tech
9347''', subject: 'Build is over', to: 'devops.anji0128@gmail.com'
}
*/
}
