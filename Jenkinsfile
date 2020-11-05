node {
  tools {
    maven 'mvn'
  }
  stage('Preparation'){
checkout scm
  }
  stage('Build'){
  
    sh "mvn install -DskipTests=true"
  }
}
