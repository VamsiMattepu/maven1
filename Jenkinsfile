node('master') 
{
  stage('ContinousDownload_Loans') 
  {
    git 'https://github.com/intelliqittrainings/maven.git'
  }
  stage('ContinousBuild_Loans') 
  {
    sh 'mvn package'
  }
 }
