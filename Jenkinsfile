node {
  stage('Preparation'){
      checkout scm
  }
  stage('Build'){
      def mvnHome = tool name: 'Apache Maven 3.6.0', type: 'maven'
      sh "${mvnHome}/bin/mvn -B -DskipTests clean package"
        sh "mvn install -DskipTests=true" 
 }
  
}
