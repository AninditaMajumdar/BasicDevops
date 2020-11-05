node {
  stage('Preparation'){
      checkout scm
  }
  stage('Build'){
      def mvnHome = tool name: 'maven', type: 'maven'
      sh "${mvnHome}/bin/mvn -B -DskipTests clean package"
 }
  
}
