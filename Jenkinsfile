node{
  tools {
    maven 'MAVEN3'
  }
  stage('SCM Checkout'){
    git 'https://github.com/ilias19/jenkins'
  }
  stage('Change version'){
    def pom = readMavenPom file: 'pom.xml'
    echo pom.version
    sh 'mvn versions:set -DremoveSnapshot'
  }
}
