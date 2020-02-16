node{
  stage('source code management'){
    git credentialsId: 'GITCredential', url: 'https://github.com/RSI1982/my-app.git'
  }
  stage('build and test'){
    def tool name: 'mavenhome', type: 'maven'
     sh "$(mavenhome)/bin/mvn package"
        }
}
