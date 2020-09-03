node('master') 
{
    stage('ContinuousDownload') 
    {
        git 'https://github.com/devopsrobin/git_jenkins.git'
    }
    stage('ContinuousBuild') 
    {
        sh label: '', script: 'mvn package'
    }
        stage('ContinuousDeployment') 
    {
       sh label: '', script: 'scp /home/ec2-user/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ec2-user@172.31.5.52:/home/ec2-user/tomcat9/webapps/qa_jenkins3.war' 
    }
         stage('ContinuousTesting') 
    {
       git 'https://github.com/devopsrobin/Testing_Jenkins.git'
       sh label: '', script: 'echo "Testing Passed"'
    }
     stage('ContinuousDelivery') 
    {
       sh label: '', script: 'scp /home/ec2-user/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ec2-user@172.31.13.57:/home/ec2-user/tomcat9/webapps/prod_jenkins3.war' 
    }
}
