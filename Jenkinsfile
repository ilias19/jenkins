node{
  stage('SCM Checkout'){
    git url:'https://github.com/ilias19/jenkins',
       branch:'develop',
       credentialsId: '123456'
  }
  
  stage('remove SNAPSHOT'){
    sh '$(grep -ri "<version>" pom.xml |head -n 1 | sed -i "s/-SNAPSHOT//g" pom.xml)'
  }
        
  stage('create and switch to release branch'){
    def version = sh '$(grep -oPm1 "(?<=<version>)[^<]+" pom.xml)'
    sh 'echo ${version}'
    //sh 'git flow release start ${version}'
  }
    
   /* withMaven( maven: 'MAVEN3'){
        sh 'mvn versions:set -DremoveSnapshot'
        sh 'git config  user.email "ilias.irhboula@gmail.com"'
        sh 'git config  user.name "ilias19"'
        sh 'git tag -a tagName2 -m "Your tag comment"'
        sh 'git commit -am "Merged develop branch to master"'
        sh 'git push origin develop'      
    }*/
}
