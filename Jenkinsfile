node {
  stage('Preparation'){
checkout scm
  }
  stage('Build'){
  
    sh "mvn install -DskipTests=true"
  }
}
