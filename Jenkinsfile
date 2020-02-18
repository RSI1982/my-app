node{
  stage('source code management'){
    git credentialsId: 'GITCredential', url: 'https://github.com/RSI1982/my-app.git'
  }
  stage('build and test'){
    def mvnhome = tool name: 'mavenhome', type: 'maven'
    sh "${mvnhome}/bin/mvn package"
        }
  stage('mail notification'){
    mail bcc: '', body: '''Hi Team,
    Please find the latest status of jenkins jobs''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job Status', to: 'err.rakeshsingh@gmail.com'
  }
  stage('sonar qube scanner'){
      withEnv(['MYTOOL_HOME=/usr/local/src/apache-maven/']) {
    sh '$MYTOOL_HOME/bin/mvn sonar:sonar'
  }
  }
}
