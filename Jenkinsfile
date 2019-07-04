node{
  stage('SCM Checkout'){
    git ('https://github.com/ilias19/jenkins','*/develop')
  }
  stage('Change version'){
    def pom = readMavenPom file: 'pom.xml'
    echo pom.version
  }
}
