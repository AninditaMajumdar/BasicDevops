node 
{
   def mvnHome = tool name: 'mvn', type: 'maven'
  stage('Preparation')
  {
      checkout scm
  }
  stage('Build')
  {
      sh "${mvnHome}/bin/mvn -B -DskipTests clean install"
  }
  stage('Sonarqube')
  {
       withSonarQubeEnv('sonarqube')
        {
            sh "${mvnHome}/bin/mvn sonar:sonar -Dsonar.host.url=https://sonarcloud.io/projects"
        }
    
  }
}
