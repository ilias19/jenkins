node{
  stage('SCM Checkout'){
    git 'https://github.com/ilias19/jenkins'
  }
  stage('Change version'){
    def pom = readMavenPom file: 'pom.xml'
    echo pom.version
    withMaven( maven: 'MAVEN3'){
       sh 'mvn versions:set -DremoveSnapshot'
      sh 'mvn scm:checkin -Dincludes=pom.xml -Dmessage="Setting version, preping for release."'
    }
  }
}
