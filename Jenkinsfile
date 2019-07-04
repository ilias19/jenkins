node{
  stage('SCM Checkout'){
    git url:'https://github.com/ilias19/jenkins',
       branch:'develop',
       credentialsId: '123456'
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
