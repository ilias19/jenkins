node{
  stage('SCM Checkout'){
    git url:'https://github.com/ilias19/jenkins',
       branch:'develop',
       credentialsId: '123456'
  }
  stage('Change version'){
    sh 'var=$(grep '<version>' pom.xml)'
    withMaven( maven: 'MAVEN3'){
        sh 'mvn versions:set -DremoveSnapshot'
        sh 'git config  user.email "ilias.irhboula@gmail.com"'
        sh 'git config  user.name "ilias19"'
        sh 'git tag -a tagName2 -m "Your tag comment"'
        sh 'git commit -am "Merged develop branch to master"'
        sh 'git push origin develop'      
    }
  }
}
