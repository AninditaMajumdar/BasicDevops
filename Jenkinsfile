node 
{
   def mvnHome = tool name: 'mvn', type: 'maven'
  stage('Preparation')
  {
      checkout scm
  }
  stage('Build')
  {
      sh "${mvnHome}/bin/mvn -B -DskipTests clean package"
  }
  stage('Sonarqube')
  {
       withSonarQubeEnv('jenkinstosonarqube')
        {
            sh "${mvnHome}/bin/mvn sonar:sonar -Dsonar.host.url=https://sonarcloud.io/projects"
        }
    
  }
}
