node('master') 
{
    stage('ContinuousDownload:multi1') 
    {
        git 'https://github.com/devopsrobin/git_jenkins.git'
    }
    stage('ContinuousBuild:multi1') 
    {
        sh label: '', script: 'mvn package'
    }
        stage('ContinuousDeployment') 
    {
       sh label: '', script: 'scp /home/ec2-user/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ec2-user@172.31.5.52:/home/ec2-user/tomcat9/webapps/qa_jenkins9.war' 
    }
}
