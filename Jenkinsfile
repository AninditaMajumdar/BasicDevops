node {
  stage('Preparation'){
      checkout scm
  }
  stage('Build'){
      withMaven(maven: 'mvn') {
        sh "mvn install -DskipTests=true" }
  }
}
