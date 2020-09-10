node('master') 
{
    stage('ContinuousDownload:Master') 
    {
        git 'https://github.com/devopsrobin/git_jenkins.git'
    }
    stage('ContinuousBuild:Master') 
    {
        sh label: '', script: 'mvn package'
    }
}
