node{
  stage('SCM Checkout'){
    git url:'https://github.com/ilias19/jenkins',
       branch:'develop',
       credentialsId: '123456'
  }
  stage('Change version'){
    sh 'version=$(grep -ri "<version>" pom.xml |head -n 1 | sed -e "s/SNAPSHOT//g" pom.xml)'
    sh 'version1=$(grep -ri "<version>" pom.xml |head -n 1);echo $version1'
    
   /* withMaven( maven: 'MAVEN3'){
        sh 'mvn versions:set -DremoveSnapshot'
        sh 'git config  user.email "ilias.irhboula@gmail.com"'
        sh 'git config  user.name "ilias19"'
        sh 'git tag -a tagName2 -m "Your tag comment"'
        sh 'git commit -am "Merged develop branch to master"'
        sh 'git push origin develop'      
    }*/
  }
}
