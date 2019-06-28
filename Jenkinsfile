node{
  stage('SCM Checkout'){
    git 'https://github.com/ilias19/jenkins'
  }
    stage('package'){
      def mvnHome=    tool name: '', type: 'maven' 
      sh "${mvnHome}/bin/mvn package"
  }
}
