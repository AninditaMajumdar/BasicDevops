node 
{
  stage('Preparation')
  {
      checkout scm
  }
  stage('Build')
  {
      def mvnHome = tool name: 'mvn', type: 'maven'
      sh "${mvnHome}/bin/mvn -B -DskipTests clean package"
  }
  stage('Sonarqube')
  {
    environment 
    {
        scannerHome = tool 'SonarQubeScanner'
    }
    steps 
    {
        withSonarQubeEnv('jenkinstosonarqube')
        {
            sh "${scannerHome}/bin/sonar-scanner"
        }
        timeout(time: 10, unit: 'MINUTES') 
        {
            waitForQualityGate abortPipeline: true
        }
    }
  }
}
