node('master') 
{
  stage('ContinousDownload_Master') 
  {
    git 'https://github.com/intelliqittrainings/maven.git'
  }
  stage('ContinousBuild_Master') 
  {
    sh 'mvn package'
  }
  stage('ContinousDeploy_Master') 
  {
    deploy adapters: [tomcat9(credentialsId: '67cdf738-32b9-4cd6-832b-f95b026bb3f3', path: '', url: 'http://172.31.7.201:8080')], contextPath: 'Qaapp', war: '**\\*.war'
  }
  stage('ContinousTesting_Master') 
  {
    git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
    sh 'java -jar /home/ubuntu/.jenkins/workspace/ScriptesPipeline/testing.jar'
  }
  stage('ContinousDelivery_Master') 
  {
   deploy adapters: [tomcat9(credentialsId: '67cdf738-32b9-4cd6-832b-f95b026bb3f3', path: '', url: 'http://172.31.4.78:8080')], contextPath: 'Proddapp', war: '**\\*.war' 
  }
}
