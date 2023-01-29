node('nodes')
{
    def mavenHome = tool name: "maven3.8.7"
    properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * *')])])
stage('CheckoutCode')
{
git branch: 'development', credentialsId: '51911611-7a53-4f9a-801e-3e26329fcdc1', url: 'https://github.com/Anjibav/maven-web-application.git'
}
stage('Build')
{
sh "${mavenHome}/bin/mvn clean package"
}
/*
stage('SonarQube Report')
{
sh "${mavenHome}/bin/mvn sonar:sonar"
}
stage('UploadArtifactintoNexus')
{
sh "${mavenHome}/bin/mvn deploy"
}
 stage('DeployAppintoTomcatServer')
  {
   sshagent(['6b7458d8-3a8a-4c77-8fad-2dce2d639a0b']) 
   {
     sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@52.66.182.81:/opt/apache-tomcat-9.0.71/webapps/"
   }
  }
  stage('sendEmailNotification')
  {
      emailext body: '''Build is over

Regards,
AJTech
9347''', subject: 'Build is over', to: 'anji.devops12@gmail.com'
  }
  */
}
