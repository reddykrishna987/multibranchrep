node('master') 
{
    stage('ContinuousDownload master') 
    {
        git 'https://github.com/selenium-saikrishna/maven.git'
    }
    stage('ContinuousBuild master') 
    {
        sh label: '', script: 'mvn package'
    }
    stage('ContinuousDeployment master')
    {
        sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.46.254:/var/lib/tomcat8/webapps/qaenv.war'
    }
    stage('ContinuousTesting master')
    {
        git 'https://github.com/selenium-saikrishna/TestingNew.git'
        sh label: '', script: 'echo "Testing Passed"'
    }
    
    stage('ContinuousDelivery master')
    {
        sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.34.187:/var/lib/tomcat8/webapps/prodenv.war'
    }
    
}
