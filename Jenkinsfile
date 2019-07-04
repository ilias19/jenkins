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
        sh 'git config  user.email "ilias.irhboula@gmail.com"'
        sh 'git config  user.name "ilias19"'
        sh 'git tag -a tagName1 -m "Your tag comment"'
        sh 'git merge develop'
        sh 'git commit -am "Merged develop branch to master"'
        sh "git push origin master"      
    }
  }
}
