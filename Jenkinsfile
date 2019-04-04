node('master') 
{
    stage('ContinuousDownload loans') 
    {
        git 'https://github.com/selenium-saikrishna/maven.git'
    }
    stage('ContinuousBuild loans') 
    {
        sh label: '', script: 'mvn package'
    }
    stage('ContinuousDeployment loans')
    {
        sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.46.254:/var/lib/tomcat8/webapps/qaenv.war'
    }
    stage('ContinuousTesting loans')
    {
        git 'https://github.com/selenium-saikrishna/TestingNew.git'
        sh label: '', script: 'echo "Testing Passed"'
    }
    
    stage('ContinuousDelivery loans')
    {
        sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.34.187:/var/lib/tomcat8/webapps/prodenv.war'
    }
    
}
